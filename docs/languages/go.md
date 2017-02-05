---
Order: 9
Area: languages
TOCTitle: Go
ContentId: 6f06908a-6694-4fad-ac1e-fc6d9c5747ca
PageTitle: Go with Visual Studio Code
DateApproved: 2/6/2017
MetaDescription: Learn about Visual Studio Code editor features (code completion, debugging, snippets, linting) for Go.
---
# Go programming with Visual Studio Code

Using the Go extension for Visual Studio Code, you get language features like IntelliSense, code navigation, symbol search, bracket matching, snippets and many other features that will help you in [Golang](https://golang.org/) development.

![go extension banner](images/go/go-extension.png)

You can install the Go extension from the VS Code [Marketplace](https://marketplace.visualstudio.com/items?itemName=lukehoban.Go).

## IntelliSense

### Auto completions

As you type in a Go file, you can see IntelliSense providing you with suggested completions.

This even works for members from packages that are not imported yet. By setting `go.autocompleteUnimportedPackages` to `true` in your [settings](/docs/customization/userandworkspace.md), you can also get all the importable packages in the suggestions.

>**Tip**: Use `kb(editor.action.triggerSuggest)` to trigger the suggestions manually.

### Hover Information

Hovering on any variable, function, or struct will give you information on that item such as documentation, signature, etc.

![Information on hover](images/go/hover.png)

By default, the extension uses `godef` and `godoc` to get this information. You can choose to use `gogetdoc` instead by changing the setting `go.docsTool` in your User or Workspace Settings.

### Signature help

When you open the `(` while calling a function, a pop-up provides signature help for the function. As you keep typing the parameters, the hint (underline) moves to the next parameter.

![Signature Help](images/go/signaturehelp.png)

>**Tip**: Use `kb(editor.action.triggerParameterHints)` to manually trigger the signature help when the cursor is inside the `()` in the function call.

The extension's signature help also uses `godef` and `godoc`. You can choose to use `gogetdoc` instead by changing the setting `go.docsTool` in your User or Workspace Settings.

## Code navigation

Code navigation features are available in the context menu in the editor.

- **Go To Definition** `kb(editor.action.goToDeclaration)` - Go to the source code of the type definition.
- **Peek Definition** `kb(editor.action.previewDeclaration)` - Bring up a Peek window with the type definition.
- **Find All References** `kb(editor.action.referenceSearch.trigger)` - Find all references for the type.

You can navigate via symbol search using the **Go to Symbol** commands from the **Command Palette** (`kb(workbench.action.showCommands)`).

- Go to Symbol in File `kb(workbench.action.gotoSymbol)`
- Go to Symbol in Workspace `kb(workbench.action.showAllSymbols)`

You can also navigate back and forth between a Go file and its test implementation using the **Go: Toggle Test File** command.

## Build, Lint and Vet

On save, the Go extension can run `go build`, `go vet` and your choice of linting tool (`golint` or `gometalinter`) on the package of the current file. You can control these features via the settings below:

- `go.buildOnSave`
- `go.buildFlags`
- `go.vetOnSave`
- `go.vetFlags`
- `go.lintOnSave`
- `go.lintFlags`
- `go.lintTool`

The errors and warnings from running any/all of the above will be shown red/green squiggly lines in the editor. These also show up in the **Problems** panel  (**View** > **Problems**).

## Formatting

You can format your Go file using `kb(editor.action.formatDocument)` or by running the **Format Document** command from the **Command Palette** or the context menu in the editor.

By default, formatting is run when you save your Go file. You can disable this behavior by setting `go.formatOnSave` to `false`.

You can choose among three formatting tools: `gofmt`, `goreturns` and `goimports` by changing the setting `go.formatTool`.

## Test

There are many test related commands that you can explore by typing "Go: test" in the **Command Palette**.

![Test Commands](images/go/testcommands.png)

The first three above can be used to generate test skeletons for the functions in the current package, file or at cursor using `gotests`. The last few can be used to run tests in the current package, file or at cursor using `go test`. There is also a command for getting test coverage.

## Import packages

Run the command **Go: Add Import** to get a list of packages that can be imported to your Go file. Choose one and it will get added in the import block of your Go file.

## Rename Symbols

You can rename symbols using `kb(editor.action.rename)` or by running the **Rename Symbol** command in the context menu in the editor.

## Next Steps

This has been a brief overview showing the Go extension features within VS Code. For more information, see the details provided in the Go extension [README](https://marketplace.visualstudio.com/items?itemName=lukehoban.Go).

If you'd like to learn more about VS Code, try these topics:

* [Visual Studio Code Basics](/docs/editor/codebasics.md) - A quick introduction to the basics of VS Code.
* [Install an Extension](/docs/editor/extension-gallery.md) - Learn about other extensions are available in the [Marketplace](https://marketplace.visualstudio.com/vscode).
* [Editing Evolved](/docs/editor/editingevolved.md) - Become a power user by mastering tips and tricks.

