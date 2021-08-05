This repository is meant to replicate a potential bug found in Tailwind v2.2.7.

### Description of issue

Some base styles are being added to the Tailwind-generated css file, even though `preflight` is disabled in `tailwind.config.js`.


### Steps to replicate

```
# clone repo
git clone https://github.com/kayewrobleski/tailwind-issue.git

# install dependencies
cd tailwind-issue
npm install

# build tailwind styles
npx tailwindcss -o build/tailwind.css
```

### Actual Behavior

The following Preflight styles appear in `build/tailwind.css`

```css
*, ::before, ::after {
  --tw-border-opacity: 1;
  border-color: rgba(229, 231, 235, var(--tw-border-opacity))
}
```

### Expected Behavior

No Preflight styles should appear in `build/tailwind.css`.
