# $var
Can be used to save a value temporary. It doesn't require setting up a new variable in the app. The data is removed after the command is executed. If value is provided the variable is set otherwise the value is retrieved. 

## Usage
```
$var[Name;(Value)]
```

## Example
We will create a command that will:
1. Set a temporary variable named `message` with the user's message.
> 🧙‍♂️ We will make it so that the entire user message is in lower case.

2. Set another variable named `id` with the ID of the message sent using `$sendMessage`, which will contain the previously set `message` temporary variable.
3. Add a button to the sent message.

```
$var[message;$toLowercase[$message]]
$var[id;$sendMessage[$var[message];yes]]
$addButton[no;interactionID;Example;secondary;no;;$var[id]]
```
![Example](https://user-images.githubusercontent.com/70456337/189480166-d37cbdb8-05ce-44e8-8f2e-14d030baa9a9.png)
