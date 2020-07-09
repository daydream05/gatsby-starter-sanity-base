# Gatsby Starter Sanity Base
A monorepo for starting a gatsby and sanity project using lerna. 

__Note:__ This starter is recommended for those familiar with using Sanity and Gatsby and would like a "clean" project to start with. I would suggest using their [official starter](https://github.com/sanity-io/example-company-website-gatsby-sanity-combo) where this project was based on, if you want to see the full power of Sanity.

## Installation

```
git clone https://github.com/daydream05/gatsby-starter-sanity-base.git

cd gatsby-starter-sanity-base

npm install

# Install or upgrade the Sanity CLI to
# make sure you are on v0.140.0 or higher

npm install -g @sanity/cli

# Set up Sanity.io account and project (≈ 45s)
npm run init
```

## The scripts

- `npm start` - runs both the studio and web's developmennt server
- `npm run graphql-deploy` -  you nteed to run this every time you make a change on your schema
- `npm run deploy` - runs graphql-deploy and deploys the studio on Sanity's server.


## What's inside
Folder structure

__web__ - Gatsby project folder

__studio__ - Sanity Studio project folder

## Using lerna

This project uses [lerna](https://github.com/lerna/lerna) to manage both Gatsby and Sanity packages inside.

### Adding a specific package to each project folder
Instead of navigating through the project folder and doing `npm install package` you have to use this command to install a new package.

#### Add package to Gatsby site
```
lerna add gatsby-plugin-webfonts --scope=web
```

#### Add package to Sanity Studio
```
lerna add react-icons --scope=studio
```

The third argument is the package you need installed. And the argument after `--scope=` is the name of the folder you want the package added

**Warning**: You cannot install multiple packages using this command. You have to install them one at a time.

```
# Can't do this
lerna add gatsby-plugin-webfonts react-icons --scope=web
```


## Common issues

### Graphql Deploy is stuck

You ran `npm run graphql-deploy` and it's stuck.

#### How to solve

You need to navigate to the `studio` folder and run `npm run graphql-deploy`

