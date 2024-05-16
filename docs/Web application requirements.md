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
- **Tab order**. The way focus is handled on the page should be clear. For search and other types of forms it is assumed that first field should receive focus by default. If there is dynamic content (e.g. expandable section) then it needs to be clarified if focus needs to be adjusted (e.g. when content is collapsed where the focus should go?).

## Text / data truncation
- Check that every piece of text displayed on the page has truncation behavior explicitly specified (truncate, fade out, truncate with ellipsis, wrap to the next line). More generically this requirement is about specifying content overflow behavior.
- Make sure that big amount of data (e.g. search results in the typeahead, input field length etc) does not affect app performance. Use limits, pagination, loading on demand, virtual scroll where applicable.

Edge cases for displayed data. It should be clear how the UI should behave in case when:
- There is no data available
- Server returned an error
- Large amount of data is available (long lists)
- Some of the data entries are long (e.g. some author has long name)
- Data is not uniform (e.g. some entries are short, some are long).

## Data loading
- Specify UI look and behavior when page data is being loaded (progress bar, spinner, loader, skeleton loader etc). Should the page be available only when data is fully loaded (i.e. route should support data pre-loading).
- Specify empty state placeholders (no data).

## Pagination
- Specify expected behavior when:  
  - Page is out of range (if page is a URL parameter).
  - All items are deleted on current page. Sometimes it make sense to reset page to the first / last available one.
- Specify selection behavior, should cross-page selection be supported? 

## Forms
- **Limits for form fields**. If input-like controls are involved then there should be clear limits / validation rules specified for each input (e.g. max number of
characters).
- Should the form be submitted upon pressing "Enter" key?
- Sync vs async form validation.

## Numbers
- **Text that includes number of items**. Plural and singular forms should be defined. E.g. "1 item selected", "2 items selected". Unless explicitly specified the rule is to use plural form as appropriate.
- Numbers formatting should be specified.

## Language
- Make sure the app uses consistent wording for the same features / concepts.
- Title case (e.g. "Author Name") should not be mixed with regular case ("Author name"). Rules need to be established for where it's appropriate to use either.

## Accessibility
- Should elements that are not actionable in the current context be disabled, hidden or visually disabled?

## Responsiveness
- **Min / max dimensions**. For dialogs and other containers that do not have fixed height/width there should be specified min / max dimensions.
- **Smaller screens**. Not only width of the view port should be taken into consideration but also the height. E.g. on some laptops modal dialogs may only appear
partially.

## Error handling
- How API failures should be handled (toasts, message boxes, 404 page etc).
- Should the online/offline connection state be watched / handled? 

## Other
- Session expiration timeout: should the user be informed beforehand that session is about to expire?
- Specify where tooltips are applicable. Use consistent tooltip wording / visual look.
- **Icons**. Icon placement inside elements (e.g. Button) should be consistent. Exceptions should be justified.
- **Colors**. Color aliases from predefined dictionary should be used and not literal RGB values (e.g. grey5 or primary-blue).
- **Cancelling dialogs / actions**. Where applicable there should be specified how the dialog (and the page that invoked the dialog) behaves upon cancelling. Should there be a confirmation message?
