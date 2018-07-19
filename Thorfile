require 'thor/group'

module Middleman
  class Generator < ::Thor::Group
    include ::Thor::Actions

    argument :name
    source_root File.expand_path(File.dirname(__FILE__))

    def copy_default_files
      # empty_directory(snake_name)
      apply_template "Gemfile.tt", "Gemfile"
      apply_template "config.rb.tt", "config.rb"
      apply_template "package.json.tt", "package.json"
      apply_template "shadow-cljs.edn.tt", "shadow-cljs.edn"
      apply_template "gitignore.tt", ".gitignore"
      apply_template "index.html.erb.tt", "source/index.html.erb"
      apply_template "layout.erb.tt", "source/layouts/layout.erb"
      apply_template "site.css.scss.tt", "source/stylesheets/site.css.scss"
      apply_template "core.cljs.tt", "source/cljs/#{snake_name}/core.cljs"
    end

    private

    def snake_name
      Thor::Util.snake_case(name)
    end

    def kebab_name
      snake_name.gsub(/_/, "-")
    end

    def apply_template(src, dest)
      template("templates/#{src}", "#{dest}")
    end
  end
end
