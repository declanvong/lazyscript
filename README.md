## Additional functionality
 - Added support for `.es6` file extensions as JS
 - Import paths that begin with leading slashes are interpreted as from the project root, not the disk root
 - Fixed type parser on JSDoc object literal types that spanned multiple lines
 - Added support for templated classes via JSDoc. Previously, `@template` could only be used for functions; they are now valid class declaration tags and will an available type within the entire class scope
 - `@typedef` tags with no identifier names are now legal, if the JSDoc comment is attached to a variable declaration with no assigned expression or initializer (identifier is inferred from the variable name)
 - `@return` statements on constructors no longer throws an error if the return type is the containing class type
  
## Todo
 - Mark JSDoc types that have type `(?T|undefined)` as optional parameters (or mark as warning only)
 - Add support for the `@interface` tag on classes
 - Interpret identifier statements as type definitions if they have a `@typedef` tag attached
