Análise de DADOS: Aula 1º



como identificar dados que falta:



Um valor ausente aparece com NaN (Not a Number) no Pandas. ANtes de tratar é preciso utilizar:



df.isnull() #True/False para cada célula.

df.isnull().sum() #total de nulos por colunas.

df.info() #mostra quantos valores não-nulos cada coluna tem.



\*melhor opção é sempre verificar os valores



\-Tratando Valores Ausentes



* **dropna**() "remove linhas ou colinas que têm o valor ausente";

&#x20;  EX:

&#x09;df.dropna()

&#x09;df.dropna(subset=\['preço1'])

&#x20;  

&#x09;# Vc pode usar isso se um dado não afetar diretamente uma somatória;



* fillna() "Preenche o valor ausente com algo(número fixo, média, texto padrão)"

&#x20;  EX:

&#x09;df\['preço'].fillna(df\['preço'].mean())

&#x09;df\['cliente'].fillna('não informado')

&#x09;

&#x09;#Use quando perder a linha inteira é pior do que estimar o valor;



\-Valores Duplicados



&#x09;Duplicata é quando a mesma linha(ou mesmo registro) aparece nas contagens



* df.duplicated()		#True para cada linha repetida
* df.duplicated().sum()	#quantas linhas repetidas existem
* df.drop.duplicated()		#remove as repetidas mas mantém a primaria





\# Cuidado com duplicata parcial

&#x09;Duas linhas podem ser "a mesma venda" mesmo sem serem idênticas em todas as colunas;







\-Tipo de Dado Errado



&#x09;Ao importar uma planilha, o Pandas às vezes, lê uma coluna numérica como texto(object), geralmente porque tem algo estranho no meio(espaço,vírgula,símbolo).





* df.dtypes			# Mostra o tipo de cada coluna
* df\['quantidade'] = df\['quantidade'].astype()
* 



