## Design System Component Tracking


### Context
- The design system is the central UX component repository for the VA. It can be found at https://design.va.gov/components/.
- In an effort to standardize our GTM tagging according to the design system, the Analytics and Insights team is specifying a data layer
to track the common user interaction associated with each component. 
- This data layer spec should be used unless an otherwise provided spec is given from the Analytics and Insights team.
- Not every design system component will have tracking, as some are dedicated to styling rather than user interaction with no tracking pieces.

### Goal
- Our bet is that by standardizing the data layer tracking code according to the design system components, this will help cut down
on the amount of time VFS and VSP teams spend in implementing the data layer and fast-track the time to begin collecting data.
- In addition, it will allow our team to spend more time on dashboarding and insights, as opposed to the implementation of tracking.

### Specification

| Component Name | Data Layer Specification 
| ------------- | ------------------------ |
Buttons | `'event': 'cta-button-click' //consistently populate for ALL types of button clicks`<br>`'button-type' //'primary', 'secondary', 'default'`<br>`'button-click-label': //dynamically populate with text of button`<br>`'button-background-color': //dynamically populate with the background color of the button`
Accordions | `'event': 'int-accordion-expand', //OR 'int-accordion-collapse'`<br>`'accordion-parent-label' //accordion parent label (if there is two labels)`<br>`'accordion-child-label': //dynamically populate with secondary label of the accordion`<br>`'accordion-section-label': //populate with the label of the section where the accordion is present`
Additional info | `'event': 'int-additionalInfo-expand', //OR 'int-additionalInfo-collapse',`<br>`'additionalInfo-click-label': //dynamically populate with the click label of the expandable component` 
Alert boxes (link click) | `'event': 'nav-alert-box-link-click' //consistent for all links within an alert box`<br>`'alert-box-type': //dynamically populate according to the type of alert box, 'warning', 'error', 'informational'`<br>`'alert-box-heading': //dynamically populate according to the top level heading of the alert box`<br>`'alert-box-alert-box-subheading': //dynamically populate according to the sub level heading of the alert box`<br>`'alert-box-click-label': //dynamically populate according to the click label of the link`<br>`'alert-box-full-width': //populate with boolean true\|false if alert box full width prop was used`<br>`'error-key': //i.e 123_description_of_error, error code and description to give context if this alert box was used in accordance with error tracking`<br>`'alert-box-background-only: //dynamically populate with boolean true\|false if alert box background only prop was used`<br>`'alert-box-closeable': //dynamically populate with boolean true\|false if the alert box is in-fact closeable`
Alert boxes (close click) | `'event': 'int-alert-box-close' //consistently populate when an alert box is closed`<br><br> **use variables listed above as well**
Alert boxes (becomes visible / alerting) | `'event': 'visibile-alert-box' //consistently populate when the alert box becomes visible`<br><br>**use variables listed above as well**
Breadcrumbs | `'event': 'nav-breadcrumb-click' //consistently populate for all breadcrumb link clicks`<br>`'breadcrumb-click-level': //integer value for the level clicked on`<br>`'breadcrumb-total-levels': //integer value with the total amount of breacrumb click labels`<br>`'breadcrumb-mobile-first-enabled': //populate if mobile first prop was used`
Featured content | `'event': 'nav-featured-content-link-click' //consistently populate for all featured content link clicks`<br>`'featured-content-heading': //dynamically populate according to the header of the featured content`<br>`'featured-content-click-label': //dynamically populate according to the link label`
Form controls - _Text Box_ | `'int-textbox-input' //consistently populate for text box inputs`<br>`'textbox-label': //dynamically populate according to the label of the text box`<br>`'textbox-input-text': //dynamically populate with the user input text`
Form controls - _Select Box_ | `'int-select-box-option-click' //consistently populate for all select box selections`<br>`'select-box-option-label': //dynamically populate according to the label of the select box`<br>`'select-box-option-click-labelint-checkbox-option-click`
Form controls - _Check Box_ | `'checkbox-label': //dynamically populate according to check box label`<br>`'checkbox-option-click-label': //dynamically populate according to link text`
Form controls - _Radio Button_ | `int-radio-button-option-click: //consistently populate for all radio button toggles`<br>`'radio-button-label': //dynamically populate according to the radio button label`<br>`'radio-button-option-click-label': //dynamically populate according to the radio button option selected`
Loading indicators | `'event': 'loading-indicator-displayed' // Loading Indicator component was displayed and is now hidden`<br>`'loading-indicator-display-time':  //populate with time (in ms) that Loading Indicator component was displayed`
Modal | `'event': 'int-modal-click': //consistently populate for modal clicks`<br>`'modal-type': //dynamically populate according to modal type, i.e 'error', 'info'`<br>`'modal-click-label': //dynamically populate according to label of button modal`<br>`'modal-button-type': //dynamically populate according to button type`<br><br> **see button types above**
Pagination | `'event': 'nav-paginate-number' //if number click, 'nav-paginate-previous' if previous click, 'nav-paginate-next' if next click`<br>`'paginate-page-number': //dynamically populate according to the number the user navigated to`<br>`'maximum-page-list-length': //populate according to the maximum number of pages that can be navigated`<br>`'last-page-enabled': //populate if last page enabled prop is used`
Progress bars | `'event': 'nav-progress-bar-change', //consistent event name for progress bar change`<br>`'progress-bar-type': 'segmented', //dynamic with type of progress bar, in this case 'segmented'`<br>`'progress-bar-current-value': //dynamically populate with an integer with each new change the current,`<br>`'progress-bar-max-value': //consistently populate as an integer with the total number of segments, i.e 5,`<br>`'progress-bar-title': //dynamically populate as a string according to the bold title next to number, i.e 'Re-Employment',`<br>`'progress-bar-subtitle': //subtitle of video, i.e 'Veteran Readiness and Employment orientation',`<br>`'enable-analytics': true //consistently populate with boolean true`
Promo banners (link click) | `'event': 'nav-promo-banner-link-click'`<br>`'promo-banner-click-label' //populate according to link click text`<br>`'promo-banner-heading': //populate with promo banner heading`
promo-banner-closeablePromo banner (closed) | `'event': 'nav-promo-banner-close'`<br><br>**reference additional variables above**
Promo banner (becomes visible) | `'event': 'visibile-promo-banner'`<br><br>**reference additional variables above**
Sidenav (parent) | `'event': 'nav-sidenav' //consistently populate for side navs`<br>`'sidenav-click-label': //populate according to sidenav clicked on `<br>`'sidenav-dropdown-header': //populate with header, undefined if parent`
Sidenav (child) | `'event': 'nav-sidenav-child'`<br><br>**see additional variables above**

