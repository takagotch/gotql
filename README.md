### gotql
---
https://github.com/khaosdoctor/gotql

```go
const gotQl = require('gotql')

const query = {
  operation: {
    name: 'users',
    fields: ['name', 'age', 'id']
  }
}

const options = {
  headers: {
    "Authorization": "Bearer <token>"
  },
  debug: false
}

gotQL.query('mygraphqlendpoint.com.br/api', query, options)
  .then(response => console.log(response.data))
  .catch(console.error)

const mutation = {
  operation {
    name: 'addLog',
    args: {
      logType: { value: 'status_change', escape: false},
      fromState: variables.fromState,
      toState: variables.toState,
      idUser: variables.idUser,
      idCampaign: variables.idCampaign,
      owner: {
        ownerType: variables.ownerType,
        username: variables.username,
        picture: variables.picture,
        name: variables.name,
        id: variables.id
      }
    },
    fields: [ 'uuid' ]
  }
}


gotQl.query(graphQLEndpoint, query, [options])

gotQl.mutation(graphQLEndpoint, query, [options])

gotQl.parser(query, type)

const response = 'query { test { name args } }'

const query = {
  name?: string;
  operation: {
    name: string;
    alias?: string;
    args?: {
      [argName: string]: any;
    } | {
      [argName: string]: {
        value: string;
        escape: boolean;
      };
    };
    fields: (string | {
      [fieldName: string]: [{
        fields?: (string | {
          [fieldName: string]: [any];
        })[];
      }];
    })[];
  };
  variables?: {
    [varName: string]: {
      type: string;
      value: string;
    };
  };
}

const query = {
  operation: {
    name: 'users',
    fields: ['name', 'age']
  }
}

const query = {
  name: 'myQuery',
  operation: {
    name: 'users',
    fields: ['name', 'age']
  }
}

const query = {
  operation: {
    name: 'user',
    ages: {
      name: 'Joe'
    }
    fields: ['name', 'age']
  }
}

const query = {
  variables: {
    name: {
      type: 'string',
      value: 'Joe'
    }
  },
  operation: {
    name: 'user',
    args: {
      name: '$name'
    }
    fields: ['name', 'age']
  }
}

const query = {
  operation: {
    name: 'users',
    fields: ['name', 'age', { friends: { fields: ['name', 'age'] }
    }]
  }
}

const query = {
  operation: {
    name: 'user',
    args: {
      type: {
        value: 'internal',
        escape: false
      }
    }
    fields: ['name', 'age']
  }
}

query { users(type: internal) { name age }}
query { users(type: "internal") { name age } }
```

```
npm install gotql

yarn install gotql
```

```
{
  "variables": {"name": "Joe"}
}
```


