# Nx NgRx Snippets

This package includes minimal snippets, to work with NgRx inside an Nrwl Nx workspace. While these snippets also work without an Nx workspace, I'd strongly encourage you to try them together with the code generation, provided by Nrwl Nx NgRx schematics.

## Features

The following snippets are included in this extension. All of them are also available in uppercase with spaces:

| Feature            | Are                                                                                 |
| ------------------ | ----------------------------------------------------------------------------------- |
| action-class       | Action class for action creation.                                                   |
| action-type        | Action type for action creation. Should be used inside `enum YourActionTypes {..}`. |
| effect             | Effect which fetches a single action and maps it to another.                        |
| effect-pessimistic | Effect performing a pessimistic update using `dataPersistence`                      |
| effect-optimistic  | Effect performing a optimistic update using `dataPersistence`                       |
| effect-navigation  | Effect listening for navigation changes using `dataPersistence`                     |
| reducer-case       | Case statement for adding a new action case to your reducer.                        |
| selector           | Selector which selects the state of your store.                                     |
| selector+loaded    | Selector which selects the state of your store and a `loaded` variable.             |

## Requirements

As said before these snippets are best used together with a Nrwl Nx Workspace and NgRx. This package makes a few assumptions, which should be met by default for Nx workspaces with Feature Stores. In the following list `[..]` refers to the name of your feature store.

- Your store files are named: `[..].actions.ts`, `[..].effects.ts`, `[..].reducer.ts` and `[..].selectors.ts`.
- Your `[..].actions.ts` includes a `[..]ActionTypes` definition.
- Your effects constructor includes `dataPersistence: DataPersistence<[..]PartialState>`.
- Your selectors include a base feature selector, selecting your whole state: `get[..]State`.
- Your selectors include a loaded selector, resolving whether your data loading is finished: `getLoaded`.
