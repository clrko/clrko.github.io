# React Admin

## Main information

### What is it?

* Front-end framework that uses React, Material UI, React Router, Redux, and React-final-form, using ES6
* Building a unified customizable admin dashboard running in the browser
* Open sourced and maintained [Marmelab](https://marmelab.com/fr/).

### How does it work?

* The admin application communicates with any API in a standardized way through data provider, whether the API uses REST, Graphql or anything else.
* Data Provider is an *adapter* for an API. It acts as the interface between them.
* It takes care of the querying and response handling between both of them.
  
![dataprovider](/assets/images/react_admin/data_provider.png)
* You can use [React-Admin's or open-sourced data providers](https://marmelab.com/react-admin/DataProviders.html#available-providers) and create your own

### Main features

* Build the app in a modular way
* One component maps one API endpoint to a CRUD interface
* Optimistic rendering
* Secure the app with the any authentication strategy (Basic Auth, JWT, OAuth, etc.)
* Translation system
* Customization / design using Material UI

### Demo

* [react-admin-demo](https://marmelab.com/react-admin-demo/#/)

### Resources

* [Official documentation on React Admin](https://marmelab.com/react-admin/Readme.html)
* [Building an admin console in react-admin](https://retool.com/blog/building-an-admin-console-in-react-admin/)
* [REST data provider used below](https://github.com/marmelab/react-admin/tree/master/packages/ra-data-simple-rest)

## Basic Tutorial

### Basic Implementation

1. Create a new project
`npx  create-react-app my_dashboard`

2. Install react-admin and your chosen data provider

[Check out this list](https://marmelab.com/react-admin/DataProviders.html)

```js
cd my_dashboard

npm install react-admin ra-data-simple-rest
// ra-data-simple-rest is the data provider 

npm start
```

### Start building the app

1. Replace the `src/App.js` with the following code and add your api.

```js
// App.js
import React from 'react'
import { Admin } from 'react-admin'
import simpleRestProvider from 'ra-data-simple-rest'

const dataProvider =  simpleRestProvider('http://path.to.my.api/')
const App = () => <Admin dataProvider={dataProvider} />

export default App;
```

This is enough for React-Admin to work. Your Browser should display the following page:

![Welcome to React Admin](/assets/images/react_admin/welcome_to_react-admin.png)

2. Now let's display the first resource

A [`<Resource>` component](https://marmelab.com/react-admin/Resource.html) maps one API endpoint to a CRUD interface. The data provider will make a request to the API `http://path.to.my.api/my_end_point`, in the example below the endpoint will be `/projects`, then display the data using the `ListGuesser` component.

```js
// App.js
import React from 'react'
import { Admin, Resource } from 'react-admin'
import simpleRestProvider from 'ra-data-simple-rest'

const dataProvider =  simpleRestProvider('http://path.to.my.api/')
const App = () => {
    return (
        <Admin dataProvider={dataProvider}>
            <Resource name="projects" list={ListGuesser}/>
        </Admin>
    )
};

export default App;
```

3. Create the first component to override the `ListGuesser` suggestion.

Using the `ListGuesser` module, the app will generate a code **in the console** that will help you create and customize the component.

You just need to copy & paste from the console the code and import fields (List, Datagrid etc.) from `react-admin'

```js
// project.js
import React from 'react'
import { List, Datagrid, TextField } from 'react-admin'

export const ProjectList = props => (
    <List {...props}>
        <Datagrid rowClick="edit">
            <TextField source="id" />
            <TextField source="name" />
            <TextField source="short_description" />
            <TextField source="long_description" />
            <TextField source="url_github_front" />
            <TextField source="url_github_back" />
            <TextField source="url_deployed" />
            <TextField source="thumbnail" />
            <TextField source="techno" />
        </Datagrid>
    </List>
);
```

You need now to update the fields with more appropriate one. You also have the possibility to [customize them](https://marmelab.com/react-admin/Theming.html).

```js
import React from 'react'
import { List, Datagrid, TextField, UrlField, EditButton } from 'react-admin'

export const ProjectList = props => (
    <List {...props}>
        <Datagrid rowClick="edit">
            <TextField source="id" />
            <TextField source="name" />
            <TextField source="short_description" />
            <TextField source="long_description" />
            <UrlField source="url_github_front" />
            <UrlField source="url_github_back" />
            <UrlField source="url_deployed" />
            <TextField source="thumbnail" />
            <TextField source="techno" />
            <EditButton />
        </Datagrid>
    </List>
);
```

1. Now, let's add an editing feature

Following the same way we did to display the data with the `ListGuesser` module, we can set up the edit feature with the `EditGuesser` module.

```js
// App.js
import React from 'react'
import { Admin, Resource, EditGuesser } from 'react-admin'
import simpleRestProvider from 'ra-data-simple-rest'
import { ProjectList } from './components/project'

const dataProvider =  simpleRestProvider('http://path.to.my.api/')
const App = () => {
    return (
        <Admin dataProvider={dataProvider}>
            <Resource name='projects' list={ProjectList} edit={EditGuesser} />
        </Admin>
    )
}

export default App;
```

1. Create our component Project Edit

As you did to list the data with the `ProjectList` component, copy and paste the generated code from the console and save it in the project folder and start customizing the fields.

```js
// project.js
export const ProjectEdit = props => (
    <Edit {...props}>
        <SimpleForm>
            <TextInput disabled source="id" />
            <TextInput source="name" />
            <TextInput multiline source="short_description" />
            <TextInput multiline source="long_description" />
            <TextInput source="url_github_front" />
            <TextInput source="url_github_back" />
            <TextInput source="url_deployed" />
            <TextInput source="thumbnail" />
            <TextInput source="techno" />
        </SimpleForm>
    </Edit>
);
```

Don't forget to update the App.js file with your editing component.

```js
import React from 'react'
import { Admin, Resource } from 'react-admin'
import simpleRestProvider from 'ra-data-simple-rest'
import { ProjectList, ProjectEdit } from './components/project'

const dataProvider =  simpleRestProvider('http://path.to.my.api/')
const App = () => {
    return (
        <Admin dataProvider={dataProvider}>
            <Resource name='projects' list={ProjectList} edit={ProjectEdit} />
        </Admin>
    )
}

export default App;
```

Please note that by default to edit a feature you need to click on the line you wish to edit but you can also enable an edit button by adding a `<EditButton />` in the Datagrid of your `ProjectList`.
