# Moxie Checkout

Moxie Checkout is a command line tool to make developing Moxie more easily. It will create a workspace with which to develop Moxie and manage individual modules on specific branches.

## Install

```
$ npm install -g moxie-checkout
```

## Usage

```
$ mc [optional selectors]
```

By default `mc` will clone and install `moxie`, then clone, install and link all dependencies of `moxie` that exist within the `moxiesuite` Github organization into a single workspace. 

## Branch Selectors

You can specify optional branch selectors when installing packages with Moxie Checkout.

There are two types of selectors: recursive selectors and one-off selectors. Examples:

1. Recursive selector. This will install `moxie` package and clone/install all relevant dependencies, switching both `moxie` and all dependencies to the `develop` branch.

    ```
    mc moxie:develop
    ```

2. One-off selector. This will install the `moxie-contract` package and clone/all all relevant dependencies. Here, `moxie-contract` will be switched to the `json-schema` branch, but its dependencies will either be left alone (if already installed), or will default to the main branch of their repository, usually `master`.  

    ```
    mc moxie-contract@json-schema
    ```
    
You can also mix selectors. For instance, the following will install `moxie` and all of its dependencies at the `develop` branch, but leave `moxie-contract` at the `json-schema` branch:

```
mc moxie:develop moxie-contract@json-schema
```
