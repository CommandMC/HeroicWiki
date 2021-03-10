Heroic is currently available in several languages listed in the [README.](https://github.com/flavioislima/HeroicGamesLauncher/blob/main/README.md)
You can help us by adding to this list!

## How to add a new translation?

1. Fork this repository.
2. Clone your fork to your computer.
3. You might want to switch to a new branch. 
4. Copy `public/locales/en` folder and rename it to your language's locale code, for example: `public/locales/hu`
5. In this folder you renamed, translate the files' content, below:
   - public/locales/hu/gamepage.json
   - public/locales/hu/login.json
   - public/locales/hu/translation.json
6. There is an array called `supportedLngs` in `electron/main.ts` and `src/index.tsx` and another array called `locales` in `i18next-parser.config.js`
   - put your language's locale code at the end of this array (in my case, it is `hu` /hungarian/)
7. To make your language selectable, put the language locale code and the name of your language **in your own language** in the array called `languageLabels` in `src/components/UI/LanguageSelector.tsx` (like this: `'es': 'Español',
    'hu': 'Magyar',` etc.)
8. Add your language's English name in `README.md` at the bottom of the list under `## Language Support`.
9. Push changes and make a PR to the `main` branch.

Huge thanks to @BiRo96 for helping us write this documentation.
Please feel free to join us on [Discord](https://discord.gg/rHJ2uqdquK) to discuss any issues you might face during this process!

You might also be asked for consent for getting pinged for maintaining translations in the future. Please see below.

## Maintaining Translations

Additionally, whenever new UI elements are added, translations are required for the texts. If you agreed to helping maintain the language you added (or any language which you are fluent in really, help is always appreciated), you will be pinged for translations.

https://github.com/flavioislima/HeroicGamesLauncher/pull/236#issuecomment-792348055 illustrates the process we use as of now.

## Have you considered things like Transifex?

We haven't decided on anything, but this way of adding translations isn't ideal, so this document might change.

---

Thanks for your support! We really appreciate your contributions to this project :D