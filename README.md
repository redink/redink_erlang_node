## rebar template for erlang release
This repo is one rebar template for erlang node release which support for easy hot upgrade.

### install

```
$ git clone https://github.com/redink/redink_erlang_node.git
$ mkdir -p ~/.rebar/template
$ cp -r redink_erlang_node/* ~/.rebar/template/
```

### uage

```
$ mkdir myapp
$ cd myapp
$ rebar create template=redink_erlang_node appid=myapp
$ rebar create-app appid=myapp
$ mv src apps/myapp/
$ tree 
.
├── apps
│   └── myapp
│       └── src
│           ├── myapp.app.src
│           ├── myapp_app.erl
│           └── myapp_sup.erl
├── rebar
├── rebar.config
├── rel
│   ├── files
│   │   ├── erl
│   │   ├── install_upgrade.escript
│   │   ├── myapp
│   │   ├── myapp.cmd
│   │   ├── nodetool
│   │   ├── start_erl.cmd
│   │   ├── sys.config
│   │   └── vm.args
│   ├── reltool.config
│   ├── reltool.config.script
│   └── reltool.config.template
└── support
    └── upgrade.sh

6 directories, 16 files
$ rebar com ; rebar generate ; ./rel/myapp/bin/myapp start
```

### ...