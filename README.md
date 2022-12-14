# NX Package-based Monorepo

```sh
npm i typescript -D -W
```

- `W` is the installation at the root

### Build each package
```sh
npx nx build is-even
```

### Link the package
```json
{
  "dependencies": {
    "is-even": "*"
  }
}
```
see with `npx nx graph`

update nx.json
```json
{
  "targetDefaults": {
    "build": {
      "dependsOn": ["^build"]
    }
  }
}
```
### Demo
```
npx nx build is-odd

npx nx run-many --target=build

npx nx run-many --target=build --skip-nx-cache
```