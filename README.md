# SRE Workbook - Markdown Templates

This is a collection of ported Markdown templates included in ["The Site Reliability Engineering Workbook"](https://landing.google.com/sre/book.html) regarding the Service Level Objectives and Error Budget Policy documents.

Full description of each section can be found in ["The Site Reliability Engineering Workbook"](https://landing.google.com/sre/book.html).

## Template List
* [Error Budget Policy Template](error-budget.md)
* [SLO Document Template](slo-document.md)

## Load templates automatically

It is possible to load the templates automatically without copy pasting from the files or manually writing the structure every time you want to author a document.

### Vim
You can add the following line into your `.vimrc` file:

    au BufNewFile error-budget-*.md 0r ~/sreworkbook-templates-md/error-budget.md

    au BufNewFile slo-*.md 0r ~/sreworkbook-templates-md/slo-document.md

### Emacs
You can add the following line into your `.emacs` file:

    (add-hook 'text-mode-hook (lambda () (when (and (string-prefix-p "slo-" (buffer-name)) (= (point-max) (point-min))) (insert-file-contents "~/sreworkbook-templates-md/slo-document.md"))))

    (add-hook 'text-mode-hook (lambda () (when (and (string-prefix-p "error-budget-" (buffer-name)) (= (point-max) (point-min))) (insert-file-contents "~/sreworkbook-templates-md/eror-budget.md"))))

In all cases, if you create a file named based on the `pattern-*`, it will load automatically the predefined template into that file. You can use any naming scheme of your choice.
