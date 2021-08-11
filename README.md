### . problems with the useEffect, useState method of data fetching from apis, not easy to tackle :
- caching the api
- polling
- refetching
- multiple calls for multiple components

### . installation
- yarn add react-query
- yarn start

### . setup (index.js)
```
import { QueryClient, QueryClientProvider } from 'react-query'
import { ReactQueryDevTools } from 'react-query/devtools'

const client = new QueryClient()

ReactDOM.render(
    <QueryClientProvider client={client}>
        <App />
        <ReactQueryDevTools />
    </QueryClientProvider>
    document.getElementById('root')
)
```
- QueryClient gives us the access you modify the query cache in react.

### . implementation ( any file )
- `import { useQuery } from 'react-query'`
- useQuery hook has 2 properties - key & request
- `key` is the name  from which we will get the cached result, fetch data, or anything we want.
- the `key` points to a resolved promise
- `Request` is a function that returns a Promise.
- `useQuery('key', REQUEST)`  `useQuery('hello', () => { // returns  a promise })`
- useQuery returns states such as `{ data, error, isLoading, isError, isSuccess, isIdle }`