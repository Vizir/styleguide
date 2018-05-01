Estilo de código é o começo para alcançarmos excelente código.

Nesta seção você irá encontrar padrões e dicas gerais.

# EditorConfig

O EditorConfig ajuda desenvolvedores a definir e manter um estilo consistente entre diferentes editores e IDEs. Ele consiste num formato de arquivo para definição de estilos de código, o `.editorconfig`, e numa coleção de plugins para diferentes editores que conseguem ler essa definição e formatar o seu código no estilo definido.

Nosso `.editorconfig` padrão é apresentado abaixo:

```ini
root = true

[*]
indent_style = space
# Unix-style line endings
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true

[*.md]
trim_trailing_whitespace = false
```

Crie esse arquivo na raíz do seu projeto e baixe o plugin de acordo com o seu editor/IDE, no link abaixo:

[http://editorconfig.org/#download](http://editorconfig.org/#download)
