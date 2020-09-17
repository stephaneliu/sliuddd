# frozen_string_literal: true

guard 'livereload' do
  extensions = {
    css: :css,
    scss: :css,
    sass: :css,
    js: :js,
    coffee: :js,
    html: :html,
    png: :png,
    gif: :gif,
    jpg: :jpg,
    jpeg: :jpeg
  }

  rails_view_exts = %w(erb haml slim)

  # file types LiveReload may optimize refresh for
  compiled_exts = extensions.values.uniq
  watch(%r{public/.+\.(#{compiled_exts * '|'})})

  extensions.each do |ext, type|
    watch(%r{
          (?:app|vendor)
          (?:/assets/\w+/(?<path>[^.]+) # path+base without extension
           (?<ext>\.#{ext})) # matching extension (must be first encountered)
          (?:\.\w+|$) # other extensions
          }x) do |m|
      path = m[1]
      "/assets/#{path}.#{type}"
    end
  end

  # file needing a full reload of the page anyway
  watch(%r{app/views/.+\.(#{rails_view_exts * '|'})$})
  watch(%r{app/helpers/.+\.rb})
  watch(%r{config/locales/.+\.yml})
end

guard 'process', name: 'Webpacker', command: 'bin/webpack' do
  watch(%r{^app/javascript/\w+/*})
end

group :rgr, halt_on_fail: true do
  guard :haml_lint, all_on_start: true do
    watch(%r{.+\.html.*\.haml$})
    watch(%r{(?:.+/)?\.haml-lint\.yml$}) { |m| File.dirname(m[0]) }
  end

  rspec_options = {
    cmd: 'bin/rspec --color --format doc',
    failed_mode: :keep,
    run_all: {
      cmd: 'COVERAGE=true DISABLE_SPRING=true bin/rspec'
    },
    all_on_start: true,
    all_after_pass: true
  }

  guard :rspec, rspec_options do
    require "guard/rspec/dsl"
    dsl = Guard::RSpec::Dsl.new(self)

    # RSpec files
    rspec = dsl.rspec

    watch(rspec.spec_helper)  { rspec.spec_dir }
    watch(rspec.spec_support) { rspec.spec_dir }
    watch(rspec.spec_files)

    # Ruby files
    ruby = dsl.ruby

    dsl.watch_spec_files_for(ruby.lib_files)

    # Rails files
    rails = dsl.rails(view_extensions: %w(erb haml slim))
    dsl.watch_spec_files_for(rails.app_files)
    dsl.watch_spec_files_for(rails.views)

    watch(rails.controllers) do |_m|
      [
        rspec.spec.call("routing/\#{m[1]}_routing"),
        rspec.spec.call("controllers/\#{m[1]}_controller"),
        rspec.spec.call("acceptance/\#{m[1]}")
      ]
    end

    # Rails config changes
    watch(rails.spec_helper)    { rspec.spec_dir }
    watch(rails.routes)         { "\#{rspec.spec_dir}/routing" }
    watch(rails.app_controller) { "\#{rspec.spec_dir}/controllers" }

    # Capybara features specs
    watch(rails.view_dirs) { |_m| rspec.spec.call("features/\#{m[1]}") }
    watch(rails.layouts)   { |_m| rspec.spec.call("features/\#{m[1]}") }

    # Turnip features and steps
    watch(%r{^spec/acceptance/(.+)\.feature$})
    watch(%r{^spec/acceptance/steps/(.+)_steps\.rb$}) do |_m|
      Dir[File.join("**/\#{m[1]}.feature")][0] || "spec/acceptance"
    end
  end

  rubocop_options = {
    all_on_start: true,
    cli: '--parallel',
    keep_failed: true
  }

  guard :rubocop, rubocop_options do
    watch(%r{.+\.rb$})
    watch(%r{(?:.+/)?\.rubocop(?:_todo)?\.yml$}) { |m| File.dirname(m[0]) }
  end

  guard 'reek' do
    watch(%r{.+\.rb$})
    watch('.reek')
  end

  brakeman_options = {
    run_on_start: true,
    quiet: true
  }

  guard 'brakeman', brakeman_options do
    watch(%r{^app/.+\.(erb|haml|rhtml|rb)$})
    watch(%r{^config/.+\.rb$})
    watch(%r{^lib/.+\.rb$})
    watch('Gemfile')
  end
end
