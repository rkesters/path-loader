[@rkesters/path-loader](README.md) / Exports

# @rkesters/path-loader

## Table of contents

### Interfaces

- [LoadCallback](interfaces/LoadCallback.md)
- [LoadOptions](interfaces/LoadOptions.md)
- [LoadOptionsBase](interfaces/LoadOptionsBase.md)
- [Loader](interfaces/Loader.md)
- [PrepareRequestCallback](interfaces/PrepareRequestCallback.md)
- [RequestCallback](interfaces/RequestCallback.md)
- [Response](interfaces/Response.md)
- [ResponseCallback](interfaces/ResponseCallback.md)

### Type Aliases

- [ProcessResponseCallback](modules.md#processresponsecallback)

### Functions

- [isLoadOptions](modules.md#isloadoptions)
- [isLoadOptionsBase](modules.md#isloadoptionsbase)
- [load](modules.md#load)

## Type Aliases

### ProcessResponseCallback

Ƭ **ProcessResponseCallback**<`T`\>: (`res`: [`Response`](interfaces/Response.md), `callback`: [`ResponseCallback`](interfaces/ResponseCallback.md)<`T`\>) => `void`

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | `any` |

#### Type declaration

▸ (`res`, `callback`): `void`

Callback used to provide access to processing the raw response of the request being made. *(HTTP loader only)*

##### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `res` | [`Response`](interfaces/Response.md) | The Superagent response object *(For non-HTTP loaders, this object will be like the Superagent        object in that it will have a `text` property whose value is the raw string value being processed.  This was done        for consistency.  There will also be a `location` property containing the location of the path being loaded.)* |
| `callback` | [`ResponseCallback`](interfaces/ResponseCallback.md)<`T`\> | Error-first callback |

##### Returns

`void`

the result of processing the responses

#### Defined in

[src/typedefs.ts:108](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L108)

## Functions

### isLoadOptions

▸ **isLoadOptions**<`T`\>(`value`): value is LoadOptions<T\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | `any` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `value` | `unknown` |

#### Returns

value is LoadOptions<T\>

#### Defined in

[src/typedefs.ts:53](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L53)

___

### isLoadOptionsBase

▸ **isLoadOptionsBase**(`value`): value is LoadOptionsBase

#### Parameters

| Name | Type |
| :------ | :------ |
| `value` | `unknown` |

#### Returns

value is LoadOptionsBase

#### Defined in

[src/typedefs.ts:21](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L21)

___

### load

▸ **load**(`location`): `Promise`<`string` \| [`Response`](interfaces/Response.md)\>

Loads a document at the provided location and returns a JavaScript object representation.

**`Example`**

```ts
// Example using Promises

PathLoader
  .load('./package.json')
  .then(JSON.parse)
  .then(function (document) {
    console.log(document.name + ' (' + document.version + '): ' + document.description);
  }, function (err) {
    console.error(err.stack);
  });
```

**`Example`**

```ts
// Example using options.prepareRequest to provide authentication details for a remotely secure URL

PathLoader
  .load('https://api.github.com/repos/whitlockjc/path-loader', {
    prepareRequest: function (req, callback) {
      req.auth('my-username', 'my-password');
      callback(undefined, req);
    }
  })
  .then(JSON.parse)
  .then(function (document) {
    console.log(document.full_name + ': ' + document.description);
  }, function (err) {
    console.error(err.stack);
  });
```

**`Example`**

```ts
// Example loading a YAML file

PathLoader
  .load('/Users/not-you/projects/path-loader/.travis.yml')
  .then(YAML.safeLoad)
  .then(function (document) {
    console.log('path-loader uses the', document.language, 'language.');
  }, function (err) {
    console.error(err.stack);
  });
```

**`Example`**

```ts
// Example loading a YAML file with options.processContent (Useful if you need information in the raw response)

PathLoader
  .load('/Users/not-you/projects/path-loader/.travis.yml', {
    processContent: function (res, callback) {
      callback(YAML.safeLoad(res.text));
    }
  })
  .then(function (document) {
    console.log('path-loader uses the', document.language, 'language.');
  }, function (err) {
    console.error(err.stack);
  });
```

#### Parameters

| Name | Type | Description |
| :------ | :------ | :------ |
| `location` | `string` | The location to the document |

#### Returns

`Promise`<`string` \| [`Response`](interfaces/Response.md)\>

Always returns a promise even if there is a callback provided

#### Defined in

[src/index.ts:150](https://github.com/rkesters/path-loader/blob/ab01c7e/src/index.ts#L150)

▸ **load**(`location`, `opts`): `Promise`<`string` \| [`Response`](interfaces/Response.md)\>

#### Parameters

| Name | Type |
| :------ | :------ |
| `location` | `string` |
| `opts` | [`LoadOptionsBase`](interfaces/LoadOptionsBase.md) |

#### Returns

`Promise`<`string` \| [`Response`](interfaces/Response.md)\>

#### Defined in

[src/index.ts:151](https://github.com/rkesters/path-loader/blob/ab01c7e/src/index.ts#L151)

▸ **load**<`T`\>(`location`, `opts`): `Promise`<`T`\>

#### Type parameters

| Name | Type |
| :------ | :------ |
| `T` | `any` |

#### Parameters

| Name | Type |
| :------ | :------ |
| `location` | `string` |
| `opts` | [`LoadOptions`](interfaces/LoadOptions.md)<`T`\> |

#### Returns

`Promise`<`T`\>

#### Defined in

[src/index.ts:152](https://github.com/rkesters/path-loader/blob/ab01c7e/src/index.ts#L152)
