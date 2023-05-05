# The Ipe extensible drawing editor

Official website: https://ipe.otfried.org/

Ipe is a drawing editor for creating figures in PDF format. It supports making small figures for inclusion into LaTeX-documents as well as making multi-page PDF presentations.

## Choosing a TeX installation

Ipe allows (and requires) that text in your figures is written in LaTeX-source, and typesets your figure by running LaTeX.  For this to work, you either need to give Ipe access to a local TeX installation, or you need to run LaTeX "in the cloud".

### Using TeX online (recommended)

Start the Ipe program, open the *Help* menu, choose *Enable online Latex-compilation*, read the explanations, and confirm.  

### Using TeX Live with the SDK (recommended)

One way to install LaTeX locally on your computer is through [org.freedesktop.Sdk.Extension.texlive](https://github.com/flathub/org.freedesktop.Sdk.Extension.texlive/), which is natively supported by this Flatpak. Just install the latest version of the SDK and it is automatically detected and used.

### Using an existing TeX Live installation (not recommended)

Sometimes it is preferred to use an existing upstream TeX Live installation. In this case an existing path can be mounted into the sandbox (given that it doesn't already exist inside) and Ipe made aware of where to find it.

```
flatpak run --filesystem=/opt/texlive/2023:ro --env=IPELATEXPATH=/opt/texlive/2023/bin/x86_64-linux org.otfried.Ipe
```

or use `override` to make it permanent

```
flatpak override --filesystem=/opt/texlive/2023:ro --env=IPELATEXPATH=/opt/texlive/2023/bin/x86_64-linux org.otfried.Ipe
```
