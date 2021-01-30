# @eth-optimism/service-base

## What is this?

`@eth-optimism/service-base` is a package that exposes a `BaseService` JavaScript class that can be used to implement various stateful JavaScript services.
Nice!

If you aren't working on the back-end side of Optimism, you probably don't need to use this package.
Otherwise, keep reading!

## Installation

### Via `npm`

```
npm install @eth-optimism/service-base --save
```

### Via `yarn`

```
yarn add @eth-optimism/service-base --save
```

## Usage

```typescript
import { BaseService } from '@eth-optimism/service-base'

interface MyServiceOptions {
    // Options to be passed into the service
}

class MyService extends BaseService<MyServiceOptions> {
    protected name = 'My Service'
    protected defaultOptions = {
        // Fill these out if you want defaults for anything
    }

    protected async _init() {
        // Do initialization logic here, will be called before anything else is run.
    }

    protected async _start() {
        // Do stuff here. Gets called inside of `service.start()`.
    }

    protected async _stop() {
        // Shut down things here. Gets called inside of `service.stop()`.
    }
}

const main = async () => {
    const service = MyService({
        // Options go here, if any.
    })

    await service.start()
}

main()
```
