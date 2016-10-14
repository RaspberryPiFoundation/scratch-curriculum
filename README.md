[![Stories in Ready](https://badge.waffle.io/codeclub/scratch-curriculum.png?label=ready&title=Ready)](https://waffle.io/codeclub/scratch-curriculum)
# Code Club Scratch Curriculum

This repository contains all the material for the [Code Club Scratch projects](https://codeclubprojects.org/en-GB/scratch/).
It consists of lesson notes and plans in [Markdown][markdown] format along with
[Scratch][scratch] project files.

__More information on our curriculum can be found [here](https://github.com/CodeClub/curriculum_documentation/blob/master/README.md).__

# New Projects

If you're a club leader trying out new projects, please complete <a href="https://docs.google.com/forms/d/1eMCfpYe3v7eYu5M8rSqLKlmq7cczLCLHx66csgyUyVU/viewform?usp=send_form" target="_blank">this short questionnaire</a> (or email projects@codeclub.org.uk) to let us know how it went!

## Contributing

This material is openly available for everyone to use and contribute to. Right now, we’re receiving translations from all over the world.

Instructions on how to contribute to our curriculum can be found [here](https://github.com/CodeClub/curriculum_documentation/blob/master/contributing.md).

## Discuss
Ask questions and share your experiences with other Code Clube World local teams in our community:
https://plus.google.com/communities/107429287353708601653

## Generating the language packs

Install dependencies

```shell
$ gem install rake rubyzip
```

Build the packs to pkg/

```shell
$ rake build
```

Or if you want to use bundler

```shell
$ bundle install
$ bundle exec rake build
```

## License

See [LICENSE.md](LICENSE.md)

## Warning

This repository uses Unicode filenames, which can break under OSX. You will need a version of Git above 1.8.2 and run `git config --global core.precomposeunicode true` before checking out the repository.

[markdown]: http://daringfireball.net/projects/markdown/
[scratch]: http://scratch.mit.edu/


