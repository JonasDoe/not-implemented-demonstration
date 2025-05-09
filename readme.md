# Demonstration of the `[ERR_METHOD_NOT_IMPLEMENTED]: The resolveSync() method is not implemented` Error
With `node@v22.14.0`, both will work, `npm run test-tsx` as well as `npm run test-ts-node`.

When switching to `@node@22.15.0`, `npm run test-ts-node` will still work, but `npm run test-tsx` with:
```
node:internal/modules/esm/module_job:400
    const namespace = this.module.evaluateSync(filename, parentFilename);
                                  ^

Error [ERR_METHOD_NOT_IMPLEMENTED]: The resolveSync() method is not implemented
    at Hooks.resolveSync (node:internal/modules/esm/hooks:323:11)
    at #resolveAndMaybeBlockOnLoaderThread (node:internal/modules/esm/loader:737:35)
    at ModuleLoader.resolveSync (node:internal/modules/esm/loader:762:52)
    at #cachedResolveSync (node:internal/modules/esm/loader:723:25)
    at ModuleLoader.getModuleJobForRequire (node:internal/modules/esm/loader:451:50)
    at new ModuleJobSync (node:internal/modules/esm/module_job:344:34)
    at ModuleLoader.importSyncForRequire (node:internal/modules/esm/loader:424:11)
    at loadESMFromCJS (node:internal/modules/cjs/loader:1561:24)
    at Module._compile (node:internal/modules/cjs/loader:1712:5)
    at Object..js (node:internal/modules/cjs/loader:1895:10) {
  code: 'ERR_METHOD_NOT_IMPLEMENTED'
}
```