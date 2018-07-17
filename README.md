# monorepo-example

For this example we will create 3 packages:

- apis
    - api 1
- components
    - component 1
    - component 2
- apps    
    - sample app

# resources

- https://yarnpkg.com/blog/2017/08/02/introducing-workspaces/

# commands
    
    yarn config set workspaces-experimental true
    
    yarn global add lerna
    yarn init
    
    lerna init
    
Tell Lerna to use yarn and yarn workspace by adding the following in `lerna.json`:

    "npmClient": "yarn",
    "useWorkspaces": true
    
Add the following in `package.json`:    
    
    "workspaces": [ "packages/*" ]

maybe better:

    "workspaces": {
        "packages": [
            "packages/*"
        ],
        "nohoist": [
            "**/react-scripts",
            "**/react-scripts/**"
        ]
    },
    
