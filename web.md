# Web code review checklist

## CSS

#### Semantic class names

[Use semantic CSS class names.](http://www.w3.org/QA/Tips/goodclassnames)

#### Non-vendor-specific properties last

[The standard CSS property should go last](http://www.456bereastreet.com/archive/201009/remember_non-vendor-prefixed_css_3_properties_and_put_them_last/) to make sure it overrides the vendor-specific ones in browsers that support both the standard and a vendor-prefixed property.
