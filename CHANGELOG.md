# CHANGELOG

- v0.1.1
  - ❌ Breaking change!  
      `buildAQL()`'s `limit` parameter no longer accepts key
      `end`, which has been renamed, per Arango spec, to `count`. The functionality
      remains the same, which is why the patch bump. Please accept my apologies
      for the un-semver approach. I have a personal philosophy that v0.X.X is
      not really subject to the standard rules of semver, but I will do my best
      to not present further breaking changes without upping at least the minor
      version. It's important for any user of the library to have a version that
      will be more compatible with all future versions going forward.
  - 🔑🗝 multi-key search  
      this can be useful if you
      have multiple fields with textual information. Theoretically, each
      chapter of a book could be stored on its own key. Or a document could
      have be translated into several languages, each stored on its own key.
      - **There are two ways to provide multiple keys to relevant functions.**
      1) `query.key` now accepts in addition to a string value, an array of
      strings over which the query is to be run. All keys listed here will be
      run combined with all collections provided to `query.collections`
      **unless** a collection has a `keys` property of its own, in which case
      **only** those keys are searched against.
      2) `query.collections[].keys` is an optional array of key names that are
      indexed by `query.collections[].analyzer`. **Note** It is important that
      any key listed in `query.collections[].keys` be indexed by the analyzer
      as it will impact results if such a key does not exist.  

