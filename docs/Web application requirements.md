# Checklist for web app requirements

Some requirements / aspect of web app functionality can be routinely overlooked when being discussed with non-technical team members. This checklist is aiming to close this gap.

## Browser window title
- What pattern should browser page (tab) title follow for application pages? E.g. `<Page name> - <Product name>`.

## UI state persistance
- Should the page state be preserved when page is reloaded? Examples:  
  - Current page number for paginated lists.
  - Sort order for sorted lists.
  - Long input text that can be in the middle of editing process.
- Should the page state be sharable with other users? Meaning users should be able to copy / paste link directly or use something like "Share" action.  
- Should page state be propagated between browser tabs? This may require data re-fetching when browser tab becomes active.

## Navigation
- Make sure it is clear how "Back" navigation button should work. E.g. Next.js framework allows to close modals with "Back" button.

## Focus management
- Should the first available interactive UI element become automatically focused when page is loaded (usually a kind of search field)? 

## Text / data truncation
- Check that every piece of text displayed on the page has truncation behavior explicitly specified (truncate, fade out, truncate with ellipsis, wrap to the next line). More generically this requirement is about specifying content overflow behavior.
- Make sure that big amount of data (e.g. search results in the typeahead, input field length etc) does not affect app performance. Use limits, pagination, loading on demand, virtual scroll where applicable.

## Data loading
- Specify UI look and behavior when page data is being loaded (progress bar, spinner, loader, skeleton loader etc). Should the page be available only when data is fully loaded (i.e. route should support data pre-loading).
- Specify empty state placeholders (no data).

## Pagination
- Specify expected behavior when:  
  - Page is out of range (if page is a URL parameter).
  - All items are deleted on current page. Sometimes it make sense to reset page to the first / last available one.
- Specify selection behavior, should cross-page selection be supported? 

## Forms

## Language
- Make sure the app uses consistent wording for the same features / concepts.

## Accessibility
- Should elements that are not actionable in the current context be disabled, hidden or visually disabled?

## Error handling


## Other
- Session expiration timeout: should the user be informed beforehand that session is about to expire?   
