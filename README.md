## Additional functionality
 - Added support for `.es6` file extensions as JS
 - Import paths that begin with leading slashes are interpreted as from the project root, not the disk root
 - Fixed type parser on JSDoc object literal types that spanned multiple lines
 - Added support for templated classes via JSDoc. Previously, `@template` could only be used for functions; they are now valid class declaration tags and will an available type within the entire class scope
 - `@typedef` tags with no identifier names are now legal, if the JSDoc comment is attached to a variable declaration with no assigned expression or initializer (identifier is inferred from the variable name)
 - `@return` statements on constructors no longer throws an error if the return type is the containing class type 
 - Mark JSDoc types that have type `(?T|undefined)` as optional parameters
 - Add support for the `@interface` tag on classes
 - Interpret identifier statements as type definitions if they have a `@typedef` tag attached
  
## Todo
 - Add support for the `@enum` tag
 - (Bug) Fix the hover text on overridden interface methods to display the correct return type (as per the implemented interface)
 - Add a warning if an optional parameter is not supplied
 - Change the error message to be "Constructor return type does not match containing class type" if a return tag on a constructor does not match
 - Check for the diagnostic errors I removed in program.ts and add them back again with more constrained checks against `NodeFlags.Hacked`
