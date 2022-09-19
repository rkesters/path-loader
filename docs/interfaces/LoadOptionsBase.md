[@rkesters/path-loader](../README.md) / [Exports](../modules.md) / LoadOptionsBase

# Interface: LoadOptionsBase

## Hierarchy

- **`LoadOptionsBase`**

  ↳ [`LoadOptions`](LoadOptions.md)

## Table of contents

### Properties

- [encoding](LoadOptionsBase.md#encoding)
- [method](LoadOptionsBase.md#method)
- [prepareRequest](LoadOptionsBase.md#preparerequest)

## Properties

### encoding

• `Optional` **encoding**: `BufferEncoding`

The encoding to use when loading the file *(File loader only)*

#### Defined in

[src/typedefs.ts:66](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L66)

___

### method

• `Optional` **method**: `string`

The HTTP method to use for the request *(HTTP loader only)*

#### Defined in

[src/typedefs.ts:70](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L70)

___

### prepareRequest

• `Optional` **prepareRequest**: [`PrepareRequestCallback`](PrepareRequestCallback.md)

The callback used to prepare the request *(HTTP loader only)*

#### Defined in

[src/typedefs.ts:74](https://github.com/rkesters/path-loader/blob/ab01c7e/src/typedefs.ts#L74)
