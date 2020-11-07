Steps to setup monorepo with rush,
[Youtube](https://www.youtube.com/watch?v=7FWG3tBTnFM&ab_channel=LeighHalliday)

- Install rush/pnpm

- rush init

- create folder apps, run create-react-app landing

- update rush.json -> projects to include the package

- rush update

- rushx start ( npm start)

- npx tsdx create components ( create componets in libs folder) \
  rushx start \
  goto tsconfig.json under libs/components, set rootDir to ./src
  add the components project to projects
  run rushx start inside components to build it

- rush update --purge ( before to make sure the projects name is the same as package.json project name)

- Goto apps to add the shared package \
  rush add --package @shared/components
  rush rebuild

- Add component

### Deploying

rush init-deploy -p landing

build

```
npm i -g @microsoft/rush && rush install && \
rush build && rush deploy --overwrite -p landing && \
cd common/deploy/apps/landing && rushx build
```

pubish

```
common/deploy/apps/landing/build
```
