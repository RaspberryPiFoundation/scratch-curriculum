desc "Create language packs in pkg/"
task :build do
  require 'rubygems'
  require 'zip/zip'
  require 'fileutils'

  STDOUT.sync = true

  here = File.expand_path('../', __FILE__)
  lang_dirs = Dir['*-*/']
  pkg_home = File.join(here, 'pkg')
  pkg_prefix = 'codeclub-term-1-scratch-'
  dir_in_zip = 'Code Club Term 1'

  FileUtils.mkdir_p(pkg_home)

  lang_dirs.each do |lang_dir|
    lang_name = File.basename(lang_dir)
    pkg_name = pkg_prefix + lang_name + '.zip'
    pkg_path = File.join(pkg_home, pkg_name)
    files = Dir[File.join(lang_dir, '**', '*.*')]

    if File.exists?(pkg_path)
      FileUtils.rm_rf(pkg_path)
    end

    Zip::ZipFile.open(pkg_path, Zip::ZipFile::CREATE) do |zipfile|
      puts "Creating #{lang_name}..."

      files.each_with_index do |file, index|
        next if file =~ /DS_Store/
        file_in_zip = File.join(dir_in_zip, file.sub(lang_dir, ''))
        zipfile.add(file_in_zip, file)
      end
    end
  end
end
