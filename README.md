## Anotações gerais
*Por Eluir Monteiro*

---
### **Git e GitHub**   
> **Git** é diferente de **GitHub**   
> O *Git* é versionamento local.   
>*GitHub* é para versionamento compartilhado.

1. git init  
> *Cria novo repositório git*

2. git status   
> *Mostra o status da branch atual*

3. git add [nome arquivo] ou git add . (pega todos os itens da pasta) 
> *Manda arquivo para stage*

4. git commit -m "minha mensagem"
> *Consolida o checkpoint "commit"*

5. git log
> *Exibe histórico de commits*

6. git reset
> *Retorna para unstage*

7. git reset idCommit
> *Retorna para pos-commit*

8. git merge [nome da branch]
> *Junta as alterações da branch nova com a main*

9. git branch -D [nome da branch]
> *Deleta a branch criada*

10. git push origin [nome da branch]
> *Envia o arquivo para o repositório online*

11. git clone [caminho do repositório]
> *Clona o repositório para um caminho local*

12. git pull
> *Atualiza os dados da main após um PR (pull request)*
---
### Python

Criação de ambiente virtual 

`python -m venv [nome_do_ambiente]`

> *Para ativar o ambiente tem que navegar até a pasta Scripts e ativar*

*Caso ocorre erro, executar este comando no* **powershell**
`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope Process`


### Arquivo executável

* Utilizando o pyinstaller   
`#pip install pyinstaller`

* comando para criar o .exe:   
`pyinstaller --onefile [nome do arquivo .py]`

* Outra variação:   
`pyinstaller - -onefile -w (que é um parametro para quando tiver janela de interação do usuário com o codigo) [nome do arquivo py]`

### Pandas

**LOC**   
É baseado em **INDEX*, ou seja, você passa o index do elemento para filtrar

**ILOC**   
É baseado na *POSIÇÃO*, ou seja, você passa qual a posição do elemento quer filtrar

### Leitura de PDF

* Biblioteca Tabula:   
`pip install tabula-py from tabula.io import read_pdf`


* Parâmetro do read_pdf:
> **GUESS** *define, ou melhor, adivinha qual parte da página estão as tabelas para leitura.   
Setar ele como `False` pode ser bom para os casos que a página toda é um arquivo tabela (por exemplo o balancete do condominio).*

* Biblioteca PyPDF2
from PyPDF2 import PdfReader 

# Abrindo um arquivo PDF existente
with open('arquivo.pdf', "rb") as input_pdf:
    # Criando um objeto PdfFileReader
    pdf_reader = PdfReader(input_pdf)

    # Obtendo o número de páginas do arquivo PDF
    num_pages = len(pdf_reader.pages)

    # Lendo o texto de cada página
    for page_number in range(num_pages):
        page = pdf_reader.pages[page_number]
        text = page.extract_text()
        print("Texto da página", page_number + 1, ":", text)