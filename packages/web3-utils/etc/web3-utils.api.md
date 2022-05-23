## API Report File for "web3-utils"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts
/// <reference types="node" />

import { keccak256 } from 'ethereum-cryptography/keccak';
import { ValidInputTypes } from 'web3-validator';

// @public (undocumented)
export type AbiInput = {
	name: string;
	type: string;
	components?: Components;
	index?: boolean;
	internalType?: string;
};

// @public (undocumented)
export type Address = HexString;

// @public (undocumented)
export type ArrayToIndexObject<T extends ReadonlyArray<unknown>> = {
	[K in IndexKeysForArray<T>]: T[K];
};

// @public (undocumented)
export const asciiToHex: (str: string) => HexString;

// @public (undocumented)
export type BlockNumberOrTag = Numbers | BlockTag;

// @public (undocumented)
export type BlockTag = 'earliest' | 'latest' | 'pending';

// @public (undocumented)
export enum BlockTags {
	// (undocumented)
	EARLIEST = 'earliest',
	// (undocumented)
	LATEST = 'latest',
	// (undocumented)
	PENDING = 'pending',
}

// @public (undocumented)
export type Bytes = Buffer | Uint8Array | ArrayBuffer | HexString;

// @public (undocumented)
export const bytesToBuffer: (data: Bytes) => Buffer | never;

// @public (undocumented)
export const bytesToHex: (bytes: Bytes) => HexString;

// @public (undocumented)
export const checkAddressCheckSum: (data: string) => boolean;

// @public (undocumented)
export const compareBlockNumbers: (blockA: Numbers, blockB: Numbers) => 1 | 0 | -1;

// @public (undocumented)
export type Components = {
	name: string;
	type: string;
	indexed?: boolean;
	components?: Components[];
};

// @public (undocumented)
export const encodePacked: (...values: TypedObject[] | TypedObjectAbbreviated[]) => string;

// @public (undocumented)
export type EncodingTypes = Numbers | boolean | Numbers[] | boolean[];

// @public (undocumented)
export type EtherUnits = keyof typeof ethUnitMap;

// @public (undocumented)
export const ethUnitMap: {
	noether: bigint;
	wei: bigint;
	kwei: bigint;
	Kwei: bigint;
	babbage: bigint;
	femtoether: bigint;
	mwei: bigint;
	Mwei: bigint;
	lovelace: bigint;
	picoether: bigint;
	gwei: bigint;
	Gwei: bigint;
	shannon: bigint;
	nanoether: bigint;
	nano: bigint;
	szabo: bigint;
	microether: bigint;
	micro: bigint;
	finney: bigint;
	milliether: bigint;
	milli: bigint;
	ether: bigint;
	kether: bigint;
	grand: bigint;
	mether: bigint;
	gether: bigint;
	tether: bigint;
};

// @public (undocumented)
export interface Filter {
	// (undocumented)
	readonly address?: Address | Address[];
	// (undocumented)
	readonly fromBlock?: BlockNumberOrTag;
	// (undocumented)
	readonly toBlock?: BlockNumberOrTag;
	// (undocumented)
	readonly topics?: (Topic | Topic[] | null)[];
}

// @public (undocumented)
export type FixedSizeArray<T, N extends number> = GrowToSize<T, [], N>;

// @public (undocumented)
export const flattenTypes: (includeTuple: boolean, puts: Components[]) => string[];

// @public (undocumented)
export const fromAscii: (str: string) => HexString;

// @public (undocumented)
export const fromDecimal: (value: Numbers) => HexString;

// @public (undocumented)
export const fromTwosComplement: (value: Numbers, nibbleWidth?: number) => number | bigint;

// @public (undocumented)
export const fromUtf8: (str: string) => HexString;

// @public (undocumented)
export const fromWei: (number: Numbers, unit: EtherUnits) => string;

// @public (undocumented)
export type GrowToSize<T, A extends Array<T>, N extends number> = {
	0: A;
	1: GrowToSize<T, _Grow<T, A>, N>;
}[A['length'] extends N ? 0 : 1];

// @public (undocumented)
export type HexString = string;

// @public (undocumented)
export type HexString16Bytes = HexString;

// @public (undocumented)
export type HexString256Bytes = HexString;

// @public (undocumented)
export type HexString32Bytes = HexString;

// @public (undocumented)
export type HexString8Bytes = HexString;

// @public (undocumented)
export type HexStringBytes = HexString;

// @public (undocumented)
export type HexStringSingleByte = HexString;

// @public (undocumented)
export const hexToAscii: (str: HexString) => string;

// @public (undocumented)
export const hexToBytes: (bytes: HexString) => Buffer;

// @public (undocumented)
export const hexToNumber: (value: HexString) => bigint | number;

// @public (undocumented)
export const hexToNumberString: (data: HexString) => string;

// @public (undocumented)
export const hexToString: (str: HexString) => string;

// @public (undocumented)
export const hexToUtf8: (str: HexString) => string;

// @public (undocumented)
export type IndexKeysForArray<A extends readonly unknown[]> = Exclude<keyof A, keyof []>;

// @public (undocumented)
export const isAddress: (value: ValidInputTypes, checkChecksum?: boolean | undefined) => boolean;

// @public (undocumented)
export const isBloom: (bloom: ValidInputTypes) => boolean;

// @public (undocumented)
export const isContractAddressInBloom: (bloom: string, contractAddress: string) => boolean;

// @public (undocumented)
export const isHex: (hex: ValidInputTypes) => boolean;

// @public (undocumented)
export const isHexStrict: (hex: ValidInputTypes) => boolean;

// @public (undocumented)
export const isInBloom: (bloom: string, value: string | Uint8Array) => boolean;

// @public (undocumented)
export const isTopic: (topic: string) => boolean;

// @public (undocumented)
export const isTopicInBloom: (bloom: string, topic: string) => boolean;

// @public (undocumented)
export const isUserEthereumAddressInBloom: (bloom: string, ethereumAddress: string) => boolean;

// @public (undocumented)
export type JsonEventInterface = {
	type: 'event';
	name: string;
	inputs: Components[];
	indexed: boolean;
	anonymous: boolean;
};

// @public (undocumented)
export type JsonFunctionInterface = {
	type: 'function';
	name: string;
	inputs: Components[];
	outputs?: AbiInput[];
	stateMutability?: string;
};

// @public (undocumented)
export const jsonInterfaceMethodToString: (
	json: JsonFunctionInterface | JsonEventInterface,
) => string;

export { keccak256 };

// @public (undocumented)
export const leftPad: (value: Numbers, characterAmount: number, sign?: string) => string;

// @public (undocumented)
export const mergeDeep: (
	destination: Record<string, unknown>,
	...sources: Record<string, unknown>[]
) => Record<string, unknown>;

// @public (undocumented)
export type Numbers = number | bigint | string | HexString;

// @public (undocumented)
export const numberToHex: (value: Numbers) => HexString;

// @public (undocumented)
export type Optional<T, K extends keyof T> = Pick<Partial<T>, K> & Omit<T, K>;

// @public (undocumented)
export const padLeft: (value: Numbers, characterAmount: number, sign?: string) => string;

// @public (undocumented)
export const padRight: (value: Numbers, characterAmount: number, sign?: string) => string;

// @public (undocumented)
export const processSolidityEncodePackedArgs: (
	arg: TypedObject | TypedObjectAbbreviated | Numbers,
) => string;

// @public (undocumented)
export const randomBytes: (byteSize: number) => Buffer;

// @public (undocumented)
export const randomHex: (byteSize: number) => string;

// @public (undocumented)
export const rightPad: (value: Numbers, characterAmount: number, sign?: string) => string;

// @public (undocumented)
export const sha3: (data: Bytes) => string | null;

// @public (undocumented)
export const sha3Raw: (data: Bytes) => string;

// @public (undocumented)
export const soliditySha3: (...values: TypedObject[] | TypedObjectAbbreviated[]) => string | null;

// @public (undocumented)
export const soliditySha3Raw: (...values: TypedObject[] | TypedObjectAbbreviated[]) => string;

// @public (undocumented)
export const stringToHex: (str: string) => HexString;

// @public (undocumented)
export const toAscii: (str: HexString) => string;

// @public (undocumented)
export const toBigInt: (value: unknown) => bigint;

// @public (undocumented)
export const toChecksumAddress: (address: Address) => string;

// @public (undocumented)
export const toDecimal: (value: HexString) => bigint | number;

// @public (undocumented)
export const toHex: (
	value: Numbers | Bytes | Address | boolean,
	returnType?: boolean | undefined,
) => HexString | ValueTypes;

// @public (undocumented)
export const toNumber: (value: Numbers) => number | bigint;

// @public (undocumented)
export type Topic = HexString32Bytes;

// @public (undocumented)
export const toTwosComplement: (value: Numbers, nibbleWidth?: number) => string;

// @public (undocumented)
export const toUtf8: (str: HexString) => string;

// @public (undocumented)
export const toWei: (number: Numbers, unit: EtherUnits) => string;

// @public (undocumented)
export type TypedObject = {
	type: string;
	value: EncodingTypes;
};

// @public (undocumented)
export type TypedObjectAbbreviated = {
	t: string;
	v: EncodingTypes;
};

// @public (undocumented)
export type Uint = HexString;

// @public (undocumented)
export type Uint256 = HexString;

// @public (undocumented)
export const utf8ToHex: (str: string) => HexString;

// @public (undocumented)
export type ValueTypes = 'address' | 'bool' | 'string' | 'int256' | 'uint256' | 'bytes' | 'bigint';

// Warnings were encountered during analysis:
//
// src/types.ts:75:2 - (ae-forgotten-export) The symbol "_Grow" needs to be exported by the entry point index.d.ts

// (No @packageDocumentation comment for this package)
```