## Instructions
1. Clone this somewhere
2. Install gulp if you don't have it already (`npm install -g gulp`)
3. Compile the compiler with `gulp local`
4. Point VSCode to this build of tsc by adding `"typescript.tsdk": "<cloned directory>/built/local"` to your VSCode user settings (or workspace settings)
5. Make sure you have a `tsconfig.json` for your source directory
6. Restart VSCode or relaunch the TSServer by running `CMD+Shift+P` => `TypeScript: Restart TS Server`

## Additional functionality
 - Added support for `.es6` file extensions as JS
 - Import paths that begin with leading slashes are interpreted as from the project root, not the disk root
 - Fixed type parser on JSDoc object literal types that spanned multiple lines
 - Added support for templated classes via JSDoc. Previously, `@template` could only be used for functions; they are now valid class declaration tags and will be an available type within the entire class scope
 - `@typedef` tags with no identifier names are now legal, if the JSDoc comment is attached to a variable declaration with no assigned expression or initializer (identifier is inferred from the variable name)
 - `@return` statements on constructors no longer throws an error if the return type is the containing class type 
 - Mark JSDoc types that have type `(...|undefined)` as optional parameters
 - Add support for the `@interface` tag on classes
 - Interpret identifier statements as type definitions if they have a `@typedef` tag attached
 - Added support for the `@enum` tag
  
## Todo

 - (Bug) Fix the symbol binding on enum declarations
 - Support for namespaced enum declarations, e.g. `SomeClass.EnumName` should emit `SomeClass` as a namespace declaration.
 - Variadic function parameters should be marked optional
 - Add support for the @inheritdoc and @private tags
 - Add a warning if an optional parameter is not supplied
 - Change the error message to be "Constructor return type does not match containing class type" if a return tag on a constructor does not match
 - Check for the diagnostic errors I removed in program.ts and add them back again with more constrained checks against `NodeFlags.Hacked`
 - Actually clean up my fixes and put them in functions so I can rebase against upstream and not die from all the conflicts
 - Rewrite all of my code as proper parse subtrees instead of rewriting nodes
