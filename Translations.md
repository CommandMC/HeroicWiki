Heroic is currently available in several languages listed in the [README.](https://github.com/flavioislima/HeroicGamesLauncher/blob/main/README.md)
You can help us by adding to this list!

## How to translate Heroic?

Right now we are using Weblate to manage all translations so if you want to add or fix translations, you will need to open an account there, translate all three main components: Global, Login, and GamePage and then commit your changes.
There are a few rules If you want to translate it:
1. For new Languages, only a 100% coverage will be accepted.
2. Languages with less than 90% coverage will be removed from Heroic while the translation its not updated until 100% again.

[Link To Weblate](https://hosted.weblate.org/projects/heroic-games-launcher/)

## How to add new translatable strings?

Heroic uses [i18next](https://www.i18next.com) to handle translations. We also use [i18next-parser](https://github.com/i18next/i18next-parser) to extract keys and default values from the code to add new keys to translation files.

The steps to add a new string that requires translations are:

### Add the string in your code using the `t` function:

```js
import { useTranslation } from 'react-i18next';

const SomeComponent = () => {
  const { t } = useTranslation();

  const myTranslatedString = t('some_key.my_key', 'My Default Value');
}

```

Guidelines:

- Check the current translation keys in `public/locales` to see if your new translation key should be nested in a group with other keys.

- Use `_` to separate keys with multiple words (snake_case)

- Don't edit the translations manually! check the next step

### Extract the keys with default values

Run `yarn i18next`, the `i18next-parser` tool will update all the files for the languages listed in `i18next-parser.config.js`.

---

Thanks for your support! We really appreciate your contributions to this project :D