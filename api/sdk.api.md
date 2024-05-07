## API Report File for "@spotify-confidence/sdk"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import { ConfidenceClientOptions } from '@spotify-confidence/client-http';
import { Configuration as FlagResolution } from '@spotify-confidence/client-http';

// Warning: (ae-forgotten-export) The symbol "Trackable" needs to be exported by the entry point index.d.ts
// Warning: (ae-missing-release-tag) "Confidence" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export class Confidence implements EventSender, Trackable {
    constructor(config: Configuration, parent?: Confidence);
    // @internal (undocumented)
    apply(resolveToken: string, flagName: string): void;
    // (undocumented)
    clearContext(): void;
    // Warning: (ae-forgotten-export) The symbol "Configuration" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    readonly config: Configuration;
    // Warning: (ae-forgotten-export) The symbol "Subscribe" needs to be exported by the entry point index.d.ts
    //
    // @internal (undocumented)
    readonly contextChanges: Subscribe<string[]>;
    // (undocumented)
    static create({ clientSecret, region, baseUrl, timeout, environment, fetchImplementation, logger, }: ConfidenceOptions): Confidence;
    // (undocumented)
    get environment(): string;
    // (undocumented)
    getContext(): Context;
    // @internal (undocumented)
    resolve(flagNames: string[]): Promise<FlagResolution>;
    // (undocumented)
    setContext(context: Context): void;
    // (undocumented)
    track(name: string, message?: Value.Struct): void;
    // Warning: (ae-forgotten-export) The symbol "Closer" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    track(manager: Trackable.Manager): Closer;
    // (undocumented)
    withContext(context: Context): Confidence;
}

// Warning: (ae-missing-release-tag) "ConfidenceOptions" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface ConfidenceOptions {
    // (undocumented)
    baseUrl?: string;
    // (undocumented)
    clientSecret: string;
    // (undocumented)
    environment: 'client' | 'backend';
    // (undocumented)
    fetchImplementation?: typeof fetch;
    // Warning: (ae-forgotten-export) The symbol "Logger" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    logger?: Logger;
    // (undocumented)
    region?: 'global' | 'eu' | 'us';
    // (undocumented)
    timeout: number;
}

// Warning: (ae-missing-release-tag) "Context" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface Context extends Value.Struct {
    // (undocumented)
    page?: {
        path: string;
        referrer: string;
        search: string;
        title: string;
        url: string;
    };
    // (undocumented)
    targeting_key?: string;
    // (undocumented)
    visitor_id?: string;
}

// Warning: (ae-missing-release-tag) "Contextual" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface Contextual<Self extends Contextual<Self>> {
    // (undocumented)
    clearContext(): void;
    // (undocumented)
    getContext(): Context;
    // (undocumented)
    setContext(context: Context): void;
    // (undocumented)
    withContext(context: Context): Self;
}

// Warning: (ae-missing-release-tag) "EventSender" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export interface EventSender extends Contextual<EventSender> {
    // (undocumented)
    track(name: string, message?: Value.Struct): void;
}

export { FlagResolution }

// Warning: (ae-missing-release-tag) "FlagResolverClient" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export class FlagResolverClient {
    // Warning: (ae-forgotten-export) The symbol "FlagResolverOptions" needs to be exported by the entry point index.d.ts
    constructor({ fetchImplementation, environment, ...options }: FlagResolverOptions);
    // (undocumented)
    apply(resolveToken: string, flagName: string): void;
    // Warning: (ae-forgotten-export) The symbol "FlagResolutionPromise" needs to be exported by the entry point index.d.ts
    //
    // (undocumented)
    resolve(context: Context, flags: string[]): FlagResolutionPromise;
}

// Warning: (ae-missing-release-tag) "pageViews" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export function pageViews(): Trackable.Manager;

// Warning: (ae-missing-release-tag) "Value" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
// Warning: (ae-missing-release-tag) "Value" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export namespace Value {
    // (undocumented)
    export function clone<T extends Value>(value: T): T;
    // (undocumented)
    export function equal(value1: Value, value2: Value): boolean;
    // (undocumented)
    export function getType(value: Value): TypeName;
    // (undocumented)
    export function isList(value: Value): value is List;
    // (undocumented)
    export function isStruct(value: Value): value is Struct;
    // (undocumented)
    export type List = ReadonlyArray<Value>;
    // (undocumented)
    export type Primitive = number | string | boolean | undefined;
    // (undocumented)
    export type Struct = {
        readonly [key: string]: Value;
    };
    // (undocumented)
    export type TypeName = 'number' | 'string' | 'boolean' | 'Struct' | 'List' | 'undefined';
}

// @public (undocumented)
export type Value = Value.Primitive | Value.Struct | Value.List;

// Warning: (ae-missing-release-tag) "visitorIdentity" is part of the package's API, but it is missing a release tag (@alpha, @beta, @public, or @internal)
//
// @public (undocumented)
export const visitorIdentity: () => Trackable.Manager;

// Warning: (ae-unresolved-link) The @link reference could not be resolved: The package "@spotify-confidence/sdk" does not have an export "Topic"
// Warning: (ae-unresolved-link) The @link reference could not be resolved: The reference is ambiguous because "track" has more than one declaration; you need to add a TSDoc member reference selector
//
// @public
export function webVitals({ lcp, inp, cls, ttfb, }?: WebVitalsOptions): Trackable.Manager;

// @public
export type WebVitalsOptions = {
    lcp?: boolean;
    inp?: boolean;
    cls?: boolean;
    ttfb?: boolean;
};

// (No @packageDocumentation comment for this package)

```