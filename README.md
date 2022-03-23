## Tree.lua
Tree.lua is a tool to navigate between instances using their properties and attributes, these functions are to extend the functionality of the Roblox Engine's built in navigation tools.


**Example Usage:**
EG 1: Look for the first child inside the parent with the Emotion attribute and a value of happy.
```lua
print(Tree.FindFirstChild(script.Parent, {
	{"Attribute", "Emotion", "happy"}
}))
```

EG 2: Find the first ancestor called `CarHOLDER`.
```lua
print(Tree.FindFirstAncestor(script, {
	{"Property", "Name", "CarHOLDER"}
}))
```

EG 3: Find the first ancestor with a script child called `MyParentIsTheHolder`.
```lua
print(Tree.FindFirstAncestor(script, {
	{"Tree", "FindFirstChild", {
		{"Property", "Name", "ITSMYPARENT"};
		{"Property", "ClassName", "Script"};
	}};
}))
```

EG 4: Find the first ancestor which is a model with a module script called `A-Chassis Tune`, this module script must have a `Plugins` folder inside it.
.. This may look complex, but just to prove it's possible.
```lua
print(Tree.FindFirstAncestor(script, {
	{"Property", "ClassName", "Model"};
	{"Tree", "FindFirstChild", {
		{"Property", "Name", "A-Chassis Tune"};
		{"Property", "ClassName", "ModuleScript"};
		{"Tree", "FindFirstChild", {
			{"Property", "Name", "Plugins"};
			{"Property", "ClassName", "Folder"};
		}};
	}}
}))
```
![enter image description here](https://cdn.discordapp.com/attachments/917223043380686850/956320873877479464/unknown.png)
