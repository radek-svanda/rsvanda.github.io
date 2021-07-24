## Today I learned

### How to manage multiple git identities


First of all you need to remove user name and email from global config

```
git config --global --remove-section user
```

Then you have to create a section for all your identities

```
git config --global user.<identity>.name "Your Full Name"
git config --global user.<identity>.email "your@email"
```

Next you create a git alias for easy identity switching

```
git config --global alias.identity = "! git config user.name \"$(git config user.$1.name)\"; git config user.email \"$(git config user.$1.email)\"; :"
```

And you are set. Now, everytime you create or clone a new repository just run

```
git identity <identity>
```
