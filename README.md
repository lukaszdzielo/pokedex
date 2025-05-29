# Vue 3 + TypeScript + Vite

This template should help get you started developing with Vue 3 and TypeScript in Vite. The template uses Vue 3 `<script setup>` SFCs, check out the [script setup docs](https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup) to learn more.

Learn more about the recommended Project Setup and IDE Support in the [Vue Docs TypeScript Guide](https://vuejs.org/guide/typescript/overview.html#project-setup).











# Pokedex
This is a project to create a Pokedex using data from the PokemonAPI. This project is for educational purposes only and is my own original code. The project is still under development, and the final form is not yet determined.

As of December 20, 2023, there are over 1000 Pokémon. I want to optimize the search so that I don't have to make a query for each one. This will involve downloading the species, special names, types, generations and a local database will be built based on this data. There are about 10 generations and 20 types, plus a number of Pokémon with names that contain spaces, hyphens, or other special characters. However, this is still less than 1000 queries. I am not using GraphQL here because the database is updated less frequently, and the Pokémon API is updated regularly. This data is stored in the local memory of the user's browser, which will significantly speed up processes in the application.

Todo list

- Databuilder
    - [ ] names
    - [ ] names with special characters
    - [ ] types
    - [ ] generations
    - [ ] img checker
- List
    - [ ] updater
- Card
    - [ ] builder
    - [ ] names
    - [ ] images
    - [ ] types
- Pagination
    - [ ] desktop list
    - [ ] desktop arrows
    - [ ] mobile select
    - [ ] mobile arrows
- Dialogs
    - [ ] show / close
- Settings dialog
    - [ ] scheme switcher
    - [ ] import / export
    - [ ] data remover / reset app