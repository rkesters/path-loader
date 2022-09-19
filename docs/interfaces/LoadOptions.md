[@rkesters/path-loader](../README.md) / [Exports](../modules.md) / LoadOptions

# Interface: LoadOptions<T\>

Options used when loading a path.

## Type parameters

| Name | Type |
| :------ | :------ |
| `T` | `any` |

## Hierarchy

- [`LoadOptionsBase`](LoadOptionsBase.md)

  ↳ **`LoadOptions`**

## Table of contents

### Properties

- [encoding](LoadOptions.md#encoding)
- [method](LoadOptions.md#method)
- [prepareRequest](LoadOptions.md#preparerequest)
- [processContent](LoadOptions.md#processcontent)

## Properties

### encoding

• `Optional` **encoding**: `BufferEncoding`

The encoding to use when loading the file *(File loader only)*

#### Inherited from

[LoadOptionsBase](LoadOptionsBase.md).[encoding](LoadOptionsBase.md#encoding)

#### Defined in

[src/typedefs.ts:66](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L66)

___

### method

• `Optional` **method**: `string`

The HTTP method to use for the request *(HTTP loader only)*

#### Inherited from

[LoadOptionsBase](LoadOptionsBase.md).[method](LoadOptionsBase.md#method)

#### Defined in

[src/typedefs.ts:70](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L70)

___

### prepareRequest

• `Optional` **prepareRequest**: [`PrepareRequestCallback`](PrepareRequestCallback.md)

The callback used to prepare the request *(HTTP loader only)*

#### Inherited from

[LoadOptionsBase](LoadOptionsBase.md).[prepareRequest](LoadOptionsBase.md#preparerequest)

#### Defined in

[src/typedefs.ts:74](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L74)

___

### processContent

• **processContent**: [`ProcessResponseCallback`](../modules.md#processresponsecallback)<`T`\>

The callback used to process the response

#### Defined in

[src/typedefs.ts:84](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L84)
