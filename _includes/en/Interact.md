DAML ledgers expose a unified API for interaction. 

**COMING SOON**

The following describes how to interact with a ledger using the <a
href="https://www.typescriptlang.org"> typescript </a> libraries `@daml/ledger`, `@daml/react` in a
frontend build with <a href="https://reactjs.org"> React </a>.

Import the libraries via:

```
import {ledger, ...} from @daml/ledger
import {useParty, ...} from @daml/react
```

React entry point:

```
const App: React.FC = () => {
  const [credentials, setCredentials] 
    = useState<Credentials | undefined>();

  return credentials
    ? <DamlLedger credentials={credentials}>
        <MainScreen onLogout=
          {() => setCredentials(undefined)}/>
      </DamlLedger>
    : <LoginScreen onLogin={setCredentials}/>;
}
```

| -------------------- | ----------------------------------------------------- |
| Get the logged in party | `const party = useParty();` <br> `...` <br> `<h1> You're logged in as {party} </h1>`|
| Exercise a choice on a contract | `const [exerciseChoice] = useExercise(ContractTemplate.ChoiceName)` <br> `...` <br> `onClick={() => exerciseChoice(contractId, arguments)}`|
| Query the ledger | `const {loading: isLoading, contracts: queryResult} = useQuery(ContractTemplate, () => ({field: value}), [party]) ` |
| Query for contract keys | `const contracts = useFetchByKey(ContractTemplate, () => key, [party])` |
| Reload the query results | `reload = useReload();` <br> `...` <br> `onClick={() => reload()}`|
