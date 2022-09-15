# mkdir for Nested Directories

We already know using `mkdir` we can create single or multiple directories from a single command, but what if we have to make nested directories from a single line command? some of you already know about `-p` or `--parents` option with `mkdir`, passing the `-p` or `--parents` with `mkdir` create parent directories as necessary, if a parent directory already exists, there will be no errors.

so let's dive into some examples.

First we'll see how we create multiple directories then we'll move to nested directories.
here we are going to create 4 directories `dir-1` `dir-2` `dir-3` `dir-4` in your current working directory.

Expected Structure:

```
├── dir-1
├── dir-2
├── dir-3
└── dir-4
```

Command:

```bash
mkdir dir-1 dir-2 dir-3 dir-4
```

---

Now we'll create nested directories and we'll start with simple structure.

Expected Structure:

```
└── src
   └── css
```

Command:

```bash
mkdir -p src/css
```

Here we have created `src` and `css` directory where `src` is our parent directory, so we have used `-p` option with `mkdir` and we have used `/` to define directory seperator.

You can increase this nested structure by using `/` and directory name.

`mkdir -p src/css/home/header/navbar`
This will create all the necessary parent categories and you'll get directories like this:

```
└── src
   └── css
      └── home
         └── header
            └── navbar
```

If you don't use `-p` option and run `mkdir src/css` then you'll get error `mkdir: src: No such file or directory` because `src` is not available but if `src` is available then you run `mkdir src/css` you won't any error because `src` is available.

---

Above we've learnt about `-p` option and basic nested struture, now we see a advance example.
so now we will create 1 parent directory and mupliple directories inside that parent directory.

Expected Structure:

```
└── src
   ├── css
   ├── fonts
   ├── images
   └── js
```

Command:

```bash
mkdir -p src/{css,js,images,fonts}
```

Here we're creating 4 directories inside `src` directory, you'll notice that we have used curly brackets`{}` and comma`(,)` for making a directory name sepration.

so now we know if we have to multiple directories in the same folder we have to use curly brackets`{}` and comma`(,)`

so you might be wondering what if you run it like this `mkdir -p src/{css/js/images/fonts}` so if you use slash`(/)` instead of comma`(,)` then `{css` & `fonts}` will be created as directory name and you'll get output similar to `mkdir -p src/css/home/header/navbar` that we have seen in previous example.

You also need to remember that `mkdir -p src/{css}` && `mkdir -p src/css` they are not same, when you have more than 1 directories to create then only you use the brackets`{}` otherwise use the normal slash`(/)`

---

Let's make it more complex, now we'll see multiple directories inside multiple direcrtories inside a parent directories.

Expected Structure:

```
└── src
   ├── css
   |  ├── blog
   |  ├── home
   |  └── post
   ├── fonts
   |  ├── mono
   |  └── serif
   ├── images
   |  ├── icons
   |  └── svgs
   └── js
      ├── admin
      └── frontend
```

Command:

```bash
mkdir -p src/{css/{home,blog,post},js/{admin,frontend},images/{icons,svgs},fonts/{mono,serif}}
```

So here we can see directories inside directoires inside a single parent directory. So rule is simple you use brackets`{}` and comma`(,)` for multiple directories and use a slash`(/)` to define parent directory of those multiple child directories.

Here are some variation & possible cases that you might use in your project:

`mkdir -p src/{scss/{mixins,modules,components},js/{admin,frontend},images,fonts}`

`mkdir -p src/{scss/{mixins,modules,components},js/{admin,frontend},images/icons,fonts}`

`mkdir -p src/{scss/{mixins,modules,components},js/frontend,images/icons,fonts}`

`mkdir -p src/{scss/{mixins,modules,components},js/{admin/vendors,frontend/{plugins,components}},images/icons,fonts}`

---

Now see this complex example based on WordPress theme structure.

Expected Structure:

```
├── assets
|  ├── css
|  ├── fonts
|  ├── images
|  └── js
├── inc
|  └── integrations
|     ├── job-manager
|     ├── ultimate-member
|     ├── visual-composer
|     |  └── shortcodes
|     └── woocommerce
|        ├── common
|        ├── loop
|        ├── order
|        ├── settings
|        ├── single
|        └── widgets
├── src
|  ├── fonts
|  ├── images
|  ├── js
|  |  ├── admin
|  |  |  └── plugins
|  |  └── frontend
|  |     ├── components
|  |     |  ├── footer
|  |     |  ├── header
|  |     |  └── post
|  |     ├── lib
|  |     └── plugins
|  └── scss
|     ├── components
|     |  ├── visual-composer
|     |  └── woocommerce
|     ├── functions
|     ├── mixins
|     └── modules
|        ├── footer
|        └── header
└── templates
   ├── comments
   |  └── meta
   ├── footer
   |  └── widegts
   ├── header
   |  ├── navbar
   |  └── search
   └── post
      └── meta
```

Command:

```bash
mkdir -p {assets/{css,js,images,fonts},src/{scss/{mixins,functions,modules/{header,footer},components/{woocommerce,visual-composer}},js/{admin/plugins,frontend/{plugins,components/{header,footer,post},lib}},images,fonts},inc/integrations/{woocommerce/{loop,single,common,order,settings,widgets},job-manager,ultimate-member,visual-composer/shortcodes},templates/{header/{navbar,search},footer/widegts,post/meta,comments/meta}}
```
