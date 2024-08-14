https://github.com/zegervdv/homebrew-zathura
##### Add repository 
```bash
brew tap zegervdv/zathura
```
```bash
brew install zathura
```
#####  Install and link one of the two plugins

> [!INFO]- For poppler
>```bash
>brew install zathura-pdf-poppler
>```
>```bash
>mkdir -p $(brew --prefix zathura)/lib/zathura
>```
>```bash
>ln -s $(brew --prefix zathura-pdf-poppler)/>libpdf-poppler.dylib $(brew --prefix zathura)/>lib/zathura/libpdf-poppler.dylib
>```



> [!INFO]- For mupdf
>```bash
>brew install zathura-pdf-mupdf
>```
>```bash
>mkdir -p $(brew --prefix zathura)/lib/zathura
>```
>```bash
>ln -s $(brew --prefix zathura-pdf-mupdf)/libpdf-mupdf.dylib $(brew --prefix zathura)/lib/zathura/libpdf-mupdf.dylib
>```

##### Copying to clipboard

*Add the following to your* 

```bash
~/.config/zathura/zathurarc:
```

```bash
set selection-clipboard clipboard
```