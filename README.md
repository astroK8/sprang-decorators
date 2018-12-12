sprang-decorators
==================

Various typescript decorators

# @Autobind

## Class decorator

```typescript
import { Autobind } from './../decorators-module';

@Autobind
export class X {

    private _myVar;

    constructor() {}

    public method1() {
        this._myVar;
    }

    public method2(v:any) {
        this._myVar=v;
    }

}
```

When method1 or method2 are called "this" will always refer to X class instance.

## Method decorator

```typescript
import { Autobind } from './../decorators-module';

export class X {

    private _myVar;

    constructor() {}

    @Autobind
    public method1() {
        this._myVar;
    }

    public method2(v:any) {
        this._myVar=v;
    }

}
```

When method1 is called "this" will always refer to X class instance.

When method2 is called "this" will depend on the context.

# @Override

```typescript
import { Trace } from './../decorators-module';

export class X {

    @Autobind
    public myMethod() {}

}

export class Y {

    @Override
    public myMethod() {}

}

```

Override decorator will check that:

- X implements myMethod

- If myMethod of X is autobinded, myMethod of Y is automatically autobinded


# @Trace

## Class decorator

```typescript
import { Trace } from './../decorators-module';

@Trace
export class X {

    private _myVar;

    constructor() {}

    public method1() {
        this._myVar;
    }

    public method2(v:any) {
        this._myVar=v;
    }

}
```

Every X instances creation + every call of methods will be logged in the console

## Method decorator

```typescript
import { Trace } from './../decorators-module';

export class X {

    private _myVar;

    constructor() {}

    @Trace
    public method1() {
        this._myVar;
    }

    public method2(v:any) {
        this._myVar=v;
    }

}
```

Every call to method1 will be logged in the console

## Property decorator

```typescript
import { Trace } from './../decorators-module';

export class X {

    @Trace
    private _myVar;

    constructor() {}

    public method1() {
        this._myVar;
    }

    public method2(v:any) {
        this._myVar=v;
    }

}
```

Every modification of _myvar will be logged in the console.









