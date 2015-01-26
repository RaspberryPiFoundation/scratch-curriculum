# Code Club Scratch Curriculum

This repository contains all the material for Term 1 and 2 of [Code Club][codeclub].
It consists of lesson notes and plans in [Markdown][markdown] format along with
[Scratch][scratch] project files.

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

[codeclub]: http://codeclubworld.org/
[markdown]: http://daringfireball.net/projects/markdown/
[scratch]: http://scratch.mit.edu/


