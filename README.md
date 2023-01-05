# Meals/Cocktails Web App

![Meals/Cocktails Web App](https://glamadelaide.com.au/wp-content/uploads/2021/04/Madam-Hanoi_chilli-fest-MEAGHAN-COLES__MC11640.jpg)

Your task is to create a web app that allows users to search for meal/cocktail recipes, store favorite ones and add new ones to DB.

## Technologie stack

### Frontend

- App logic (choose your option):
  - [React](https://reactjs.org/)
  - [Next.js](https://nextjs.org/)
  - [Vue.js](https://vuejs.org/) (* only if you need to learn it)
  - [Angular](https://angular.io/) (* only if you need to learn it)
- Data fetching & store (choose your option):
  - [React Query](https://react-query-v3.tanstack.com/)
  - [Redux Toolkit](https://redux-toolkit.js.org/)
  - [tRPC client](https://trpc.io/docs/quickstart) + [Zustand](https://github.com/pmndrs/zustand)
- UI component library
- Typescript
- ESLint, Prettier, and Pre-commit
- Hosted on (choose your option):
  - [GitHub pages](https://pages.github.com/)
  - [Render](https://render.com/)
  - [Vercel](https://vercel.com/)
  - [Netlify](https://www.netlify.com/)

### Backend

- API Server (choose your option):
  - [Express.js](https://expressjs.com/)
  - [tRPC Server](https://trpc.io/docs/quickstart) (* if you have chosen tRPC client on front)
  - [Next.js API server](https://nextjs.org/docs/api-routes/introduction)
  - [GraphQL](https://graphql.org/)
- ORM (choose your option):
  - [Sequalize ORM](https://sequelize.org/)
  - [Prisma](https://www.prisma.io/)
- [PostgreSQL](https://www.postgresql.org/) database hosted on (choose your option):
  - [ElephantSQL](https://www.elephantsql.com/)
  - [Fly.io](https://fly.io/), [how to docs](https://medium.com/data-folks-indonesia/setup-free-postgresql-on-fly-io-and-import-database-3f8f891cbc71) (* free, but needs credit card on registration)
  - [Supabase](https://supabase.com/)
  - [Bit.io](https://bit.io/)
  - Provided by hosting (read docs)
- Hosted on (choose your option):
  - [Render](https://render.com/)
  - [Vercel](https://vercel.com/)
  - [Adaptable](https://adaptable.io/)
- Typescript
- ESLint, Prettier, and Pre-commit

## Roadmap

- Setup your development environments for client and server
- Decide if you will work with monorepo or multi-repo ([article #1](https://geekflare.com/code-repository-strategies/), [article #2](https://kinsta.com/blog/monorepo-vs-multi-repo/#monorepo-vs-multirepo-how-to-choose))
- Initialize empty frontend project using:
  - [Create React App](https://create-react-app.dev/)
  - [Vite](https://vitejs.dev/)
  - [Create Next App](https://nextjs.org/docs/api-reference/create-next-app) (* if you have chosen Next.js)
- Initialize empty backend project
- Create a GitHub repo(s) and connect it with your project
- Install all necessary dependencies
- Configure typescript, linter, prettier, etc
- Create a dummy frontend page with the `Hello world!` text and run it. Check if all works correctly.
- Create a dummy backend endpoint with the `Hello world!` text and request it. Check if all works correctly.
- Choose UI library and API (read next chapter)
- Test external API endpoints directly or use [Postman](https://www.postman.com/)
- Write a step-by-step plan for your development. **Add a realistic deadline to your calendar!** It will take 3-5 working days to complete this task.
- Start developing, feature-by-feature, commit-by-commit (remember, you need to have a nice commit history!).
- Test your application
- When completed, create an extended `readme.md` file(s) ([example](https://gist.github.com/solaryasha/0fb46a864b490afd618f2c4751a65041), [constructor](https://readme.so/)) for both frontend and backend parts
- Deploy your project so it can be viewed online
- Ask the mentor to give you feedback
- Add project to your portfolio
- Profit!

## API

You can choose between two APIs:
- [Meals](https://www.themealdb.com/api.php)
- [Cocktails](https://www.thecocktaildb.com/api.php)

*These APIs are free to use. If you want some additional features - you can pay $2. Read more about it in API docs.*

Your choice will determine what your app will be:
- Cooking app
- Party app

## Design & theme

Choose the UI component library you like:
  - [Grommet](https://v2.grommet.io/)
  - [Material UI](https://mui.com/)
  - [React Bootstrap](https://react-bootstrap.github.io/)
  - [Chakra UI](https://chakra-ui.com/)
  - [React Bulma](https://react-bulma.dev/en)
  - [Semantic UI React](https://react.semantic-ui.com/)

You can find basic app design [here](). It doesn't have styles and strict limitations - use it only as a reference. The overall look of your app depends on the UI library and your own ideas.

Additional icons you can use:
- [Choose any here](https://iconscout.com/blog/best-react-icons-library)

Generate color theme for your app: [Use palette generator](https://coolors.co/generate)

**Try not to use the default UI kit colors! Your app needs to be unique, so use different colors!**

## Features

### Basic rules

1. Your app needs to have 3 DB tables:
  - `Users` table:
    - Name
    - Email
    - Salt
    - Hashed_password
  - `Tokens` table:
    - RefreshToken
    - UserId
  - `Meals` or `Cocktails` table:
    - ...fields same as provided by API
    - ...custom fields (decide what fields you want to add)
    - CretedByUser (true/false)
    - UserId
2. Check if the user is authorized before showing page content
3. Show the **Sign-in page** if the user isn't authorized
4. Show the **404 page** for unknown routes 

Use this [Mate Academy topic](https://mate.academy/learn/nodejs/auth-nodejs) to learn about authorization.

### Sign-in page

1. Show the form centered on the screen
2. Show the `Sign-in` <> `Register` switch
3. When `Sign-in` is active show only the `Email` and `Password` fields. On submit check entered user data:
  - proceed to the **Main page** if email & password are correct (issue new auth token)
  - show error message in other cases
4. When `Register` is active show the `Name`, `Email`, `Password`, and `Repeat password` fields. On submit check entered user data:
  - all fields are required and can't be empty
  - passwords should match
  - email needs to be correct and unique (no such user in DB)
  - proceed to the **Main page** if all fields are correct (issue new auth token)
  - show error message in other cases

### Main page

1. Page consists of two parts:
  - Left sidebar (occupies full window height)
  - Content (vertically scrollable)
2. Sidebar consists of:
  - App logo
  - Filter section, that contains form divided into parts (only one can be active at a time):
    - Search by title (text input field)
    - Filter by ... fields (text input field with suggestions in dropdown select - look for available data in API docs)
      - For example: `Filter by Category` will be a dropdown select with a list of all available categories and input fields, so the user can type text and filter that list. He can select a category from the filtered list.
    - `Submit` button (active if the user entered/selected something)
    - `Clear` button (active after the user submitted the form)
  - `My list` button (scrolls content to user's list section)
  - `Add new` button (shows modal with a form to add new entity)
  - `Log out` button (clear token and shows the **Sign-in page**)
  - Contacts section:
    - Icons & links to your GitHub, LinkedIn, and Facebook profiles
3. Content consists of sections:
  - `Search/Filter results` OR `Random item`:
    - If the user didn't submit the serach/filter form, show the random item from the API
    - If the user submitted the form, show results **both** from API and user list as cards
    - If no data is found or error - show a message instead of results
    - If the user cleared the form - show the new random item from the API
    - Show only 12 first items and the `Show more` button
    - On the `Show more` button click show 3 more items, and repeat until there are items to show
  - `My list`:
    - If no entries in the list or error - show a message
    - Show items as cards
    - Add infinite scroll or pagination for this list (add support on the backend side for this feature)

#### Item card

Item card consists of the parts:
- Title
- Heart icon OR Trash bin icon:
  - If the item is from an external API show heart:
    - Outlined - if it's not in the user's list
    - Filled - if it's already in the user's list

      * When a user clicks on outlined heart icon - add it to your DB and show it in `My list`, fill in the heart
      * When a user clicks on the filled heart icon - remove the item from DB, remove it from `My list`, and make the heart outlined
  - If the item is created by the user (it has the `CreatedByUser` property and it equals to `true`) show the Trash bin icon:
      * When a user clicks on the icon remove the item from the DB and `My list` 
- Item photo
- Main details (such as `Category`, `Area`, `Tags`, `Glass` etc., but not a recipe or video…)
- `Details` button:
  - On click show the **Details** modal or page (decide what is the best approach for you)

#### Details modal / page

- Show all available details about the item, such as a recipe, ingredients, video, custom fields, etc
- Show the `Add to My List` / `Remove from My List` / `Delete item` button (depends on what item you are looking at now)
- Show the `Edit item` button for items from My List.

#### Mew item | Edit item modal

- Show form with all necessary fields
- Make some fields required (title, category, photo, recipe, etc)
- User needs to provide a URL to image for new recipe (don't store images on server! just check if the URL is correct and try to request image from it), also he can change existing one
- Add a couple of custom fields. Some ideas:
  - Cooking time
  - Rating
  - Number of portions
  - Complexity
  - Best for
  - ...
