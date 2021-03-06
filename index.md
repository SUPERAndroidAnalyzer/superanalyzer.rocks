---
layout: page
title: SUPER Android Analyzer
---
{% include JB/setup %}

<img src="{{ site.production_url }}/assets/logo.png" alt="SUPER logo" title="SUPER Android Analyzer" style="float:left;width:15em;margin:1em">

*Secure, Unified, Powerful and Extensible Rust Android Analyzer*

**Welcome to SUPER!** Here you can find all the information relevant to the SUPER Android Analyzer.
You can find news too, and of course, the downloads. SUPER is a command-line application that can
be used in Windows, MacOS X and Linux, that analyzes *.apk* files in search for vulnerabilities. It
does this by decompressing APKs and applying a series of rules to detect those vulnerabilities.

SUPER has been developed in [Rust](https://www.rust-lang.org/), a systems programming language that
gives performance similar to well-written C/C++, while avoiding memory leaks, data races, and
giving memory safety. This programming language was selected to improve all the Java or Python based
alternatives. It also gives us the ability to perform much more powerful checks faster.

<form style="text-align:center" action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_top">
<input type="hidden" name="cmd" value="_s-xclick">
<input type="hidden" name="hosted_button_id" value="K32C48SSW3VB6">
<input type="image" src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" border="0" name="submit" alt="PayPal - The safer, easier way to pay online!">
<img alt="" border="0" src="https://www.paypalobjects.com/es_ES/i/scr/pixel.gif" width="1" height="1">
</form>

<div style="clear:both"></div>

## Usage

Using SUPER is really simple:

```
super {apk_file}
```

If SUPER is installed in the current directory, in Unix, you will need to run `./super` instead.

This will decompress all the files in the `dist/{package_name}` folder, analyze them with the rules
in the `rules.json` file (and configuration in the `config.toml` file) and generate the results in
the `results/{package_name}` folder.

In the results page, an `index.html` file will contain the report, while a `report.json` file will
have a machine readable format of that report. In the case of using the *verbose* mode (see below),
the report will also be shown in the terminal.

You can learn about more specific use cases by running:

```
super --help
```

You can also configure in the `config.toml` file the paths of `vendor`, `downloads` and other
folders. If the package was installed using one of the provided packages, the default configuration
will usually simply work. If not, probably the same folder where `super` is called from will work
(usually the installation folder, or the current workspace). If willing to use other paths, a
sample configuration file can be found in the `config.toml.sample` file.

Lots of parameters can be configured in that file, such as the threads that will be used for the
analysis or the rule file. We currently require some Java dependencies that are included in the
packages. This should change once [#22](https://github.com/SUPERAndroidAnalyzer/super/issues/22) is
implemented.

## Latest news

<ul class="posts">
  {% for post in site.posts %}
    <li><time datetime="{{ post.date | date: "%Y-%m-%d" }}">{{ post.date | date_to_string }}</time> » <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
