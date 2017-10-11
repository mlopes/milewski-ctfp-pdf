# TODO

As part of the work to generate an epub, and subsequently a mobi, there's
quite a lot of work yet needed before this becomes anywhere near usable.
I'm currently focusing on getting this to generate something that can be used,
and then improve how it's done, and add the missing non essential content
(cover, preamble, postamble, etc...)

- [x] Image paths are not found when generating epub because they're not relative to `src/` root
- [X] Missing title
- [ ] Missing TOC causes kindlegen export to fail
- [ ] Missing cover
- [ ] Missing preamble because of the file causing an error when generating the epub
- [ ] Figure why it doesn't work using the `ctfp.tex` file
- [ ] Improve how images are being added to epub (the whole copying files and force removing the folder is a bit clumsy)
