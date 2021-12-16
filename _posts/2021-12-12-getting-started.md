---
title: ការចាប់ផ្តើមកម្មវិធីវេបសាយ
author:
  name: "យ៉ាន សមរាជ"
  link: https://github.com/samreachyan
date: 2021-12-12 20:55:00 +0700
categories: [Tutorial, Setup]
tags: [Installation]
pin: true
---

## ក្រេឌីតអ្នកផលិត

`Template` វេបសាយនេះត្រូវបានប្រើប្រាស់តាមគំរូរបស់ [Jekyll Docs](https://jekyllrb.com/docs/installation/) ដោយប្រើ [Chirpy Theme](https://github.com/cotes2020/jekyll-theme-chirpy) អ្នកអាចរៀបធ្វើវាពីដំណាក់កាលដំបូងបានដោយត្រូវដំឡើងកម្មវិធីចាំបាច់មួយចំនួន `Ruby`, `RubyGems`, `Jekyll`, និង `Bundler` ។

### ប្រព័ន្ធប្រតិបត្តិការ Ubuntu / Linux

ចូលប្រើ Command Line ដើម្បីដំឡើងបណ្ណាល័យសំខាន់ៗ៖

```console
$ sudo apt-get install ruby-full build-essential zlib1g-dev
```

ដាក់បន្ថែម PATH របស់ environment ដើម្បីដំឡើងកម្មវិធីរបស់អ្នក៖

```console
$ echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
$ echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
$ echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
$ source ~/.bashrc
```

រាល់មុនការចាប់ផ្តើមគម្រោងរបស់វេបសាយ Jekyll ត្រូវប្រើ វានឹងទាញយក Library ទៅក្នុងថតឯក vendor៖

```console
$ gem install jekyll bundler
```

## តោះដំឡើង

### ទាញយកពី Github

Source Code ទាំងអស់ត្រូវបានបង្ហាញជាសាធារណៈ ហើយអាចទាញយកមកប្រើបានដោយប្រើប្រាស់ Command Line ៖

```console
$ git clone https://github.com/samreachyan/samreachyan.git
```

### ដំណើរការកម្មវិធី

បន្ទាប់ចូលក្នុងថតឯកសារបានទាញយក៖

```console
$ cd samreachyan
$ gem install jekyll bundler
$ bundle install                  #ទាយយក dependencies/library
$ bundle exec jekyll serve        #ដំណើរការ
```

### ការកែតម្រូវ និងបញ្ចូលបន្ថែម

ចូលអ្នកកែក្នុងឯកសារឈ្មោះ `_config.yml` ហើយប្តូរពត៌មានសំខាន់មួយចំនួនតាមលំនាំដើម៖

- `url` ជាតំណភ្ជាប់របស់វេបសាយអ្នក
- `avatar` ជាតំណភ្ជាប់រូបភាពរបស់អ្នក
- `timezone` ជាល្វែងម៉ោងតាមតំបន់
- `lang` ជាភាសាដែលត្រូវកំណត់ជាមួយវេបសាយអ្នក

សម្រាប់ភាសាខ្មែរ និង អង់គ្លេង

```console
$ _data/locales/en.yml
$ _data/locales/km.yml
```

សង្កេតមើល៖

- `author > name`
- `author > bio`

### កែរូបរាង Stylesheet

ប្រសិនបើអ្នកចង់កែលំអបន្ថែមទៀតអាចចូល `assets/css/style.scss` វាហ្នឹង Generate ឯកសារនោះទៅតាម template ដែលយើងបានកំណត់ស្រាប់។

### ដំណើរការ Local Server

យើងអាចមើលលទ្ធផលនៃការដំណើរការ៖

```console
$ bundle exec jekyll serve
```

ឬដំណើរការជាមួយ Docker:

```console
$ docker run -it --rm \
    --volume="$PWD:/srv/jekyll" \
    -p 4000:4000 jekyll/jekyll \
    jekyll serve
```

យើងបើក Browser រួចចូលក្នុងតំណ _<http://127.0.0.1:4000>_.
