# useMotionTransitions

useMotionTransitions is used to **handle** the multiple **animations** created when you animate your **elements**.

It exposes `push` and `stop` which are both **functions**.

## Exposed

### `push(key, value, target, transition)`

Push function **run** and **add** a transition to the current useMotionTransitions **instance**.

### `stop(keys | key | undefined)`

Stop is a **function** that lets you **stop** ongoing **animations** for a specific **element**.

Calling it **without** argument will be stopping **all** the **animations**.

Calling it with an **array** of [**Motion Properties**](/motion-properties) keys will stop **every** specified **key**.

Calling it with a **single** motion property key will stop the specified **key**.

## Example

```typescript
const target = ref<HTMLElement>()

const { motionProperties } = useMotionProperties(target)

motionProperties.x = 0

const { push, stop } = useMotionTransitions()

push('x', 100, motionProperties, { type: 'spring', bounce: 4 })

setTimeout(stop, 4000)
```
