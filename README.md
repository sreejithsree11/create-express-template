# CREATE-EXPRESS-TEMPLATE

Create a modern express server with a simple command.

![Working sample](https://media.giphy.com/media/MC9h5ruPM0Wk7lJyxQ/giphy.gif)

Works on macOS, Windows, and Linux. Has both TypeScript and JavaScript templates inbuild. Creates all the boilerplate code along with build process and unit tests configured so that you can focus on the application logic.

Optionally, add the ORM for database support and also configure dependency injection.

# USAGE

```
$ npx create-express-template my-app
$ cd my-app
$ npm start
```

We strongly suggest using npx from for npm versions 5.2+. You can also install create-express-template globally and use it to create a template anywhere in your system.

After starting, go to http://localhost:3000/ to see a simple page(3000 here being the port number, you can change this in the .env file). We also implement a sample route at http://localhost:3000/api/v1/users so you can start building immediately following the pattern.

## Highlights

- [Usage with options](#usage-with-options)
- [Templates](#templates)
- [Under the hood](#under-the-hood)
- [Contributing](#contributing)

## Usage with options

```
$ npx create-express-template --help 

    Usage
	  $ create-express-template <FolderName>

	  FolderName can be:
	    Folder name can be anything without a space

	Options
      --template            Name of the template(default:TypeScript)
      --default(-d)         Use default template
      --yarn(-y)            Use Yarn

	Examples
	  $ create-express-app
	  $ create-express-app my-app
	  $ create-express-app my-app -d
	  $ create-express-app my-app --template="TypeScript-Inversify-TypeORM" -y
      $ create-express-app my-app --template="tsti" -y

```

The `folderName` and the `template` will be prompted to the user via the interactive ui in case these are not specified. 

Using the `default` option will use TypeScript as the template. If you aren't already using TypeScript, read about why you should start using it [here](https://serokell.io/blog/why-typescript).

If you want to use `yarn` as your package manager, specify the `yarn` option.

The available templates(and what each of them should be user for) are listed [here](#templates).

## Templates

| Template                      | Initials    | Details         
| :---                          |    :----:   | :---          
| JavaScript                    | js          | Plain JavaScript Template          
| JavaScript-Sequelize          | jss         | JS + [Sequelize](https://sequelize.org) 
| TypeScript                    | ts          | Plain TypeScript Template          
| TypeScript-TypeORM            | tst         | TS + [TypeORM](https://typeorm.io/#/)            
| TypeScript-Inversify          | tsi         | TS + [Inversify](https://github.com/inversify/InversifyJS)
| TypeScript-TypeORM-Inversify  | tsit, tsti  | TS + [Inversify](https://github.com/inversify/InversifyJS) + [TypeORM](https://typeorm.io/#/)           

We use [Sequelize](https://sequelize.org) for JavaScript and [TypeORM](https://typeorm.io/#/) for TypeScript and both are excellent ORMs. You can check out their pages for more information on creating models and writing queries.

[Inversify](https://github.com/inversify/InversifyJS) is an excellent and lightweight inversion of control container for JavaScript & Node.js apps powered by TypeScript. For people unfamiliar with why you would want to have [Inversion of control](https://medium.com/@amitkma/understanding-inversion-of-control-ioc-principle-163b1dc97454), this one and many other articles can be found on the topic. Read up more on [Dependency Injection](https://www.freecodecamp.org/news/a-quick-intro-to-dependency-injection-what-it-is-and-when-to-use-it-7578c84fa88f/) and why and when you should use it to understand why `inversify` helps in building modern applications.