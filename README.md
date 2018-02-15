## Additional functionality
 - Added support for `.es6` file extensions as JS
 - Import paths that begin with leading slashes are interpreted as from the project root, not the disk root
 - Fixed type parser on JSDoc object literal types that spanned multiple lines
 - Added support for templated classes via JSDoc. Previously, `@template` could only be used for functions; they are now valid class declaration tags
 - `@typedef` tags with no identifier names are now legal, if the JSDoc comment is attached to a variable declaration with no assigned expression or initializer (identifier is inferred from the variable name)
  
## Todo
 - Mark JSDoc types that have type `(?T|undefined)` as optional parameters (or mark as warning only)
 - Allow `@return` statements on constructors (or mark as warning only)
 - Allow empty bodies with no return statements in classes marked as interfaces
 - Interpret identifier statements as type definitions if they have a `@typedef` tag attached
