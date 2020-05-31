# py-fsm

A very simple Python Finite State Machine implementation.

## Usage

Create a Finite State Machine:

```python
fsm = FiniteStateMachine(python_dict)
```

Alternatively, load one straight from a .json file:

```python
fsm = FiniteStateMachine.load_from_file("my_fsm.json")
```

Where your dict/.json is formatted like so:

```json
{
	"state":
  	{
  		"action":"resulting_state",
  		"action_2":"resulting_state_2"
  	}
}
```

So, say for example an fsm for a lock could be:

```json
{
	"locked":
		{
			"unlock":"unlocked"
		},
	"unlocked":
		{
			"lock":"locked"
		}
}
```

You need not set actions for states if they don't change the current state, for example locking while in the locked state, however you can if you prefer.

You can also iterate over `FiniteStateMachine` instances:

```python
for state, actions in fsm:
	print(state, actions)
```
