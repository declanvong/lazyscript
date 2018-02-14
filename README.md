## Additional functionality
 - Added support for `.es6` file extensions as JS
 - Import paths that begin with leading slashes are interpreted as from the project root, not the disk root
 - Fixed type parser on JSDoc object literal types that spanned multiple lines
  
## Todo
 - Mark JSDoc types that have (?T|undefined) as optional parameters
 - Implement templated classes via JSDoc (currently, @template can only be used for functions)
