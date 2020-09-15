# Code Climate Standard Engine

[![Code Climate](https://codeclimate.com/github/codeclimate/codeclimate-standard/badges/gpa.svg)](https://codeclimate.com/github/codeclimate/codeclimate-standard)

`codeclimate-standard` is a Code Climate engine that wraps the [Standard](https://github.com/rubocop-hq/rubocop) static analysis tool. You can run it on your command line using the Code Climate CLI, or on our hosted analysis platform.

RuboCop helps you enforce many of the guidelines outlined in the community [Ruby Style Guide](https://github.com/rubocop-hq/ruby-style-guide). Most aspects of its behavior can be tweaked via various [configuration options](https://github.com/rubocop-hq/rubocop/blob/master/config/default.yml), which are set in a **.rubocop.yml** file.

You can find some basic setup instructions and links to the Standard OSS project below. For additional Code Climate-specific config details, check out our [Standard engine documentation][cc-docs-standard].

### Installation

1. If you haven't already, [install the Code Climate CLI](https://github.com/codeclimate/codeclimate).
2. Run `codeclimate engines:enable standard`. This command both installs the engine and enables it in your `.codeclimate.yml` file.
3. You're ready to analyze! Browse into your project's folder and run `codeclimate analyze`.

### Need help?

For help with Standard, [check out their documentation](https://github.com/testdouble/standard).

If you're running into a Code Climate issue, first check out [our Standard engine docs][cc-docs-standard] and look over this project's [GitHub Issues](https://github.com/codeclimate/codeclimate-standard/issues), as your question may have already been covered. If not, [go ahead and open a support ticket with us](https://codeclimate.com/help).

[cc-docs-standard]: https://docs.codeclimate.com/docs/standard
