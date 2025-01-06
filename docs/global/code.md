# Vamos ao Código 👨🏼‍💻

## Padronização de Código

* **Por que seguir uma padronização de código?** 🤔

Seguir uma boa padronização do código garante muito mais do que simplesmente um padrão, **garante facilidade ao ser replicado, lido e repassado para os demais desenvolvedores e mantenedores do código.**

Com isso em mente, devemos seguir um padrão, no qual pode ser lido nos seguintes links:

- [Guia de Programação Python | Google](https://android.googlesource.com/platform/external/google-styleguide/+/refs/tags/android-s-beta-2/pyguide.md)

Os pontos que as documentações acima trazem são importantes para os desenvolvimentos, mas alguns são **obrigatoriamente necessários** quando estamos desenvolvendo, listamos eles logo abaixo:

- **Nomes claros e objetivos:** sempre precisamos definir claramente o que aquela variável ou função vai fazer, não simplesmente definir nomes aleatórios, pois isso pode dificultar a compreensão futuramente. Da mesma forma, nunca misture idiomas, sempre use 100% do seu código em inglês ou 100% em português.
    - **Evite:** nomes somente com letras únicas e nomes muitos genéricos, como `a` e `b` ou `var1` e `var2`
        
        > Em casos que as variáveis seguem um padrão, como em fórmulas e iterações, pode-se utilizar de nomes comuns, como `i`, `j` e `x`
    
    - **Sempre defina bem os nomes que vamos utilizar para não evitar confusões**
        - Nomes claros e objetivos são essenciais para um bom código 
    
    - Fique atento:
        - Clean Code é uma leitura recomenda
        - [Clean Code: Significado e Importância para Desenvolvimento](https://blog.casadodesenvolvedor.com.br/o-que-e-clean-code/)

- **Type Hints:** é necessário para sabermos quais são os tipos de dados que estão trafegando pelas funções, classes e demais estruturas do código. Com ele, podemos facilmente compreender os tipos que devemos enviar para o nosso código.

    - Algumas referências: 
        - [PEP 484 – Type Hints](https://peps.python.org/pep-0484/)
        - [Google Python Style Guide](https://android.googlesource.com/platform/external/google-styleguide/+/refs/tags/android-s-beta-2/pyguide.md#:~:text=2.21%20Type%20Annotated%20Code)
        - [Type hints cheat sheet - mypy 1.8.0 documentation](https://mypy.readthedocs.io/en/stable/cheat_sheet_py3.html)

- **Organização do código:** sempre atentar-se às definições que são feitas no código, pois facilmente podemos gerar alguns bugs que, com um código mal organizado, tornam-se difíceis de corrigir.
    - Fique ligado:
        - Execute o `pylint` ou o `ruff` sobre seu código para encontrar bugs e definições faltando, siga os pontos que forem retornados para você e garanta que seu código esteja o melhor possível
        - [Google Python Style Guide](https://android.googlesource.com/platform/external/google-styleguide/+/refs/tags/android-s-beta-2/pyguide.md)
        - [6 Python Best Practices for Better Code | DataCamp](https://www.datacamp.com/blog/python-best-practices-for-better-code)
        - [PEP 8 – Style Guide for Python Code](https://peps.python.org/pep-0008/)

- **Lembre-se de sempre utilizar processos eficientes**

- **Use e abuse do Git:** _todos os códigos devem estar versionados com o Git_, **sem exceções.** Caso não possua repositório para subir, solicite ao PL ou TL. Todos os códigos devem estar em um repositório, não há exceções.

- **Use formatadores para organizar o código:** Existem vários formatadores que podemos usar para dar aquele tapa no código, use-os para garantir que todos que lerem seu código, possam entender mais facilmente o que está acontecendo.
    - Exemplos:
        - ruff 💡 Recomendado
        - yapf
        - black

## Documentação do Código

> “O código é lido com mais frequência do que escrito.” - Guido van Rossum

Com esse pensamento em mente, precisamos desenvolver sempre pensando em duas coisas: atingir o objetivo do desenvolvimento e deixar claro o que está sendo feito. Desta forma, é importante termos em mente esses pontos para garantirmos que nosso código possa ser lido com facilidade pelos próximos desenvolvedores.

Dessa forma, podemos seguir padrões já definidos para o desenvolvimento, como docstrings, tipagem das variáveis, comentários sucintos e READMEs para documentar os projetos. Alguns links para entendermos como seguir os padrões:

- [Style guide — numpydoc v1.7.0rc0.dev0 Manual](https://numpydoc.readthedocs.io/en/latest/format.html)

- [Documenting Python Code: A Complete Guide](https://realpython.com/documenting-python-code/)

Devemos sempre tentar acompanhar os pontos acima para garantir que estejamos seguindo o melhor caminho ao desenvolver. Alguns pontos que são necessariamente importantes:

- **Docstrings:** fundamental para as funções e métodos, são definidas na PEP 257, os objetos python precisam ser documentados para conseguirmos entender os objetivos daquela função ou objeto. Para outras linguagens, deve-se buscar formas de documentação padrão para o seu código.

- **Tipagem:** por conta do python ser uma linguagem dinâmica, é necessário identificar os tipos de variáveis e retornos de funções, pois facilitam o entendimento. Para outras linguagens que são fortemente tipadas, não faz necessário, mas para linguagens dinâmicas, a identificação do tipo é muito importante.

- **Comentários em código:** importante serem feitos de forma sucinta, só para indicar lógicas que são complexas de serem interpretadas.

