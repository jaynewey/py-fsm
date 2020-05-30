# py-fsm

A very simple Python Finite State Machine implementation.

## Usage

Create a Finite State Machine:

```
fsm = FiniteStateMachine(python_dict)
```

Alternatively, load one straight from a .json file:

```
fsm = FiniteStateMachine.load_from_file("my_fsm.json")
```

Where your dict/.json is formatted like so:

```
{
	"state":
  	{
  		"action":"resulting_state",
  		"action_2":"resulting_state_2"
  	}
}
```

So, say for example an fsm for a lock could be:

```
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
