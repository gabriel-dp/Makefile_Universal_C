# Makefile Universal C

Makefile é um arquivo de texto que contém um conjunto de instruções para a construção e compilação de um software.

O Makefile contém uma lista de regras que especificam como o software deve ser construído a partir de seus arquivos-fonte. Cada regra descreve um conjunto de arquivos de entrada e as ações que devem ser executadas para produzir um arquivo de saída.

Este repositório tem o objetivo de padronizar a estrutura de projetos de tamanho pequeno/médio em C.

&nbsp;

## 📁 Estrutura dos arquivos

Todos os arquivos são dividos em diretórios específcos de acordo com sua função no programa final.

- `bin` - Diretório do arquivo executável
- `build` - Diretório dos objetos de compilação (.o)
- `include` - Diretório dos arquivos de cabeçalho (.h)
- `src` - Diretório dos arquivos de implementação (.c)

Não é recomendável enviar os arquivos dos diretórios `bin` e `build` ao compartilhar o projeto.

> Para evitar que os arquivos sejam publicados em um repositório Git, inclua as pastas no arquivo `.gitignore`

&nbsp;

## 🛠 Compilação e Vinculação

Por padrão, o compilador definido é o `gcc`, podendo ser alterado editando a constante de definição no arquivo.

```md
# Defines C Compiler
CC := gcc
```

```md
# Compiler flags
CFLAGS := -Wall -I $(INCDIR)

# Linker flags
LDFLAGS := -lm
```

### Flags de compilação

- `-Wall` - Habilita o aviso de todos o possíveis problemas na compilação (variáveis não utilizadas, conversões de tipo inseguras, entre outros).

- `-I` - Especifica um diretório de inclusão de cabeçalhos (no caso o `include`).

### Flags de vinculação

Especificam opções adicionais que serão passadas ao linker durante a fase de vinculação de um programa. Algumas bibliotecas necessitam que sejam adicionadas suas flags de vinculação, como a `math.h`.

- `-lm` - Vincula a biblioteca matemática padrão do sistema.

&nbsp;

## 📑 Instruções de uso

Para utilizar o `Makefile` basta adicioná-lo ao projeto em desenvolvimento e executar o comando:

```cmd
make
```

Importante destacar que é necessário que o projeto esteja organizado de acordo com a estrutura definida acima.

### Clean

O arquivo inclui também suporte à exclusão das pastas `bin` e `build` de forma automática, basta executar o comando:

```cmd
make clean
```

> É recomendado excluir objetos de compilação toda vez que trocar a branch do projeto, evitando conflitos.
