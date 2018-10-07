require 'thor/group'

module Middleman
  class Generator < ::Thor::Group
    include ::Thor::Actions

    NULL = RbConfig::CONFIG['host_os'] =~ /mingw|mswin/ ? 'NUL' : '/dev/null'

    argument :name
    source_root File.expand_path(File.dirname(__FILE__))

    def copy_default_files
      apply_template "Gemfile.tt", "Gemfile"
      apply_template "README.md.tt", "README.md"
      apply_template "config.rb.tt", "config.rb"
      apply_template "karma.conf.js.tt", "karma.conf.js"
      apply_template "package.json.tt", "package.json"
      apply_template "Rakefile.tt", "Rakefile"
      apply_template "shadow-cljs.edn.tt", "shadow-cljs.edn"
      apply_template "gitignore.tt", ".gitignore"
      apply_template "index.html.erb.tt", "source/index.html.erb"
      apply_template "layout.erb.tt", "source/layouts/layout.erb"
      apply_template "site.css.scss.tt", "source/stylesheets/site.css.scss"
      apply_template "core.cljs.tt", "source/cljs/#{snake_name}/core.cljs"
      apply_template "sample_test.cljs.tt", "tests/cljs/#{snake_name}/test/sample_test.cljs"
    end

    def install_js_dependencies
      # TODO: Detect if npm or yarn is being used instead of assuming yarn
      run "yarn install"
    end

    private

    def snake_name
      Thor::Util.snake_case(name)
    end

    def kebab_name
      snake_name.gsub(/_/, "-")
    end

    def titleized_name
      snake_name.split("_").map(&:capitalize).join(" ")
    end

    def apply_template(src, dest)
      template("templates/#{src}", "#{dest}")
    end

    def has_git?
      system("git --version >#{NULL} 2>&1")
    end

    def author
      if has_git?
        `git config user.name`.chomp
      else
        say "\nNo Git executable found. Using result of `whoami` as author name."
        `whoami`.chomp
      end
    end
  end
end
