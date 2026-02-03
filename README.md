# Central Food & Drinks - Hugo Site

A multilingual restaurant menu website built with Hugo static site generator.

## Features

- 🌐 **Multilingual Support**: Portuguese (default) and English
- 📱 **Responsive Design**: Works on all devices
- 🚀 **Fast Loading**: Static HTML pages
- 📝 **Easy Content Management**: Menu items in TOML files
- 🔄 **Automatic Deployment**: GitHub Actions to GitHub Pages

## Project Structure

```
site-hugo/
├── config.toml           # Hugo configuration
├── data/
│   └── menu/            # Menu data files
│       ├── cafetaria.toml
│       ├── drinks.toml
│       ├── food.toml
│       └── snacks.toml
├── i18n/                # UI translations
│   ├── pt.toml         # Portuguese
│   └── en.toml         # English
├── layouts/             # HTML templates
├── static/
│   └── css/            # Stylesheets
└── content/            # Page content files
```

## How to Update Menu Items

### Edit Menu Data Files

All menu items are stored in TOML files in the `data/menu/` directory:

1. **Cafetaria** (`data/menu/cafetaria.toml`): Coffee, tea, and hot beverages
2. **Drinks** (`data/menu/drinks.toml`): Alcoholic beverages, wines, beers, soft drinks
3. **Food** (`data/menu/food.toml`): Toasts, salads, hamburgers, bowls
4. **Snacks** (`data/menu/snacks.toml`): Seafood snacks and specialties

### Menu Item Format

For items with the same name in both languages:
```toml
[[items]]
id = "cappuccino"
price = "2,50 €"
name = "Cappuccino"
```

For items with different names per language:
```toml
[[items]]
id = "espresso"
price = "1,30 €"

[items.name]
pt = "Café"
en = "Espresso"
```

For items with descriptions:
```toml
[[toasts]]
id = "tuna_toast"
price = "8,00 €"

[toasts.name]
pt = "Tosta de Atum"
en = "Tuna Toast"

[toasts.description]
pt = "Atum c/ Maionese, Queijo, Tomate e Ovo"
en = "Tuna with Mayo, Cheese, Tomato and Boiled Egg"
```

## Local Development

### Prerequisites

- Hugo (extended version): [Install Hugo](https://gohugo.io/getting-started/installing/)

### Running Locally

```bash
# Navigate to the site directory
cd site-hugo/

# Start the Hugo development server
hugo server

# Visit http://localhost:1313 for Portuguese
# Visit http://localhost:1313/en/ for English
```

### Building the Site

```bash
# Build the static site
hugo

# The generated files will be in the public/ directory
```

## Deployment

The site is automatically deployed to GitHub Pages when you push to the main branch.

### Setup GitHub Pages (First Time Only)

1. Go to your repository on GitHub
2. Navigate to Settings → Pages
3. Under "Build and deployment", select "GitHub Actions" as the source
4. Push changes to the main branch
5. The site will be available at: `https://[username].github.io/[repository]/`

### Updating the Live Site

1. Make changes to menu items or templates
2. Test locally with `hugo server`
3. Commit and push changes:
   ```bash
   git add .
   git commit -m "Update menu items"
   git push
   ```
4. GitHub Actions will automatically build and deploy the site

## URL Structure

- Portuguese (default): `https://[username].github.io/[repository]/`
- English: `https://[username].github.io/[repository]/en/`

## Customization

### Changing Prices

Edit the price field in the corresponding TOML file:
```toml
price = "2,50 €"  # Change to new price
```

### Adding New Items

Add a new item block to the appropriate TOML file:
```toml
[[items]]
id = "new_item"
price = "3,00 €"

[items.name]
pt = "Nome em Português"
en = "English Name"

[items.description]  # Optional
pt = "Descrição"
en = "Description"
```

### Modifying UI Text

Edit the translation files in `i18n/`:
- `i18n/pt.toml` for Portuguese UI text
- `i18n/en.toml` for English UI text

## Notes

- The site uses flag emojis (🇵🇹 🇬🇧) in the language switcher
- Smooth scrolling navigation is preserved from the original design
- The design remains identical to the original site
- No JavaScript is needed for language switching (pure static HTML)

## Support

For Hugo documentation, visit: https://gohugo.io/documentation/