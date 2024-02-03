- 👋 Hi, I’m @juliaciva
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
juliaciva/juliaciva is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
[Uploading exercic
#include <stdio.h> // bilbioteca de comunica�ao com o usuario
#include <stdlib.h> // biblioteca de aloca�ao de espa�o em mem�ria
#include <locale.h> //bilbioteca de aloca�oes de texto por regi�o
#include <string.h> //biblioteca respons�vel por cuidar das string

int registro() //Fun��o respons�vel por cadastrar os usu�ios no sistema
{
	//In�cio da cria��o de vari�veis/string
	char arquivo[40];
	char cpf[40];
	char nome[40];
	char sobrenome[40];
	char cargo[40];
	//Final da cria��o de vari�veis/string
	
	printf("Digite o CPF a ser cadastrado\n"); //Coletendo informa��o do usu�rio
	scanf("%s",cpf);//%s refere-se a string/estamos armazenando as string
	
	strcpy(arquivo, cpf); //respons�vel por copiar os arquivos das string
	
	FILE *file; // cria o arquivo 
	file = fopen(arquivo, "w"); //cria o arquivo/ w vem de write escrever
	fprintf(file,cpf);//salvo o valor da vari�vel
	fclose(file); //fecha o arquivo
	
	file = fopen(arquivo, "a"); //cria o arquivo
	fprintf(file,","); //coloca a virgula
	fclose(file);// fecha o arquivo
	
	printf("Digite o nome a ser cadastrado: \n"); //coletando informa��es do usu�rio
	scanf("%s",nome);//armazena a string
	
	file = fopen(arquivo, "a"); //cria o arquivo
	fprintf(file,nome);//salva o valor da variavel/no caso o nome
	fclose(file);// fecha o arquivo
	
	file = fopen(arquivo, "a");//cria o arquivo
	fprintf(file,",");//coloca a virgula
	fclose(file);//fecha o servi�o
	
	printf("Digite o sobrenome a ser cadastrado\n");//coletando informa��es do usu�rio
	scanf("%s",sobrenome);// armazena na string
	
	
	file  = fopen(arquivo, "a");//cria o arquivo
	fprintf(file,sobrenome);//salva o valor da variavel/no caso o sobrenome
	fclose(file);//fecha o servi�o
	
	file = fopen(arquivo, "a");//cria o arquivo
	fprintf(file,",");//coloca a virgula
	fclose(file);//fecha o servi�o
	
	printf ("Digite o cargo a ser cadastrado: \n");//coletando informa��es do usu�rio
	scanf("%s",cargo); //armazena na string
	
	file = fopen(arquivo, "a");//cria o arquivo
	fprintf(file,cargo);//salva o valor da vari�vel
	fclose(file);//fecha o servi�o
	
	system("pause");//pausa o servi�o
			
}

int consulta()
{
	setlocale(LC_ALL, "Portuguese");//definindo a linguagem
	
	//inicio da cria��o das vari�veis/string
	char cpf[40]; 
	char conteudo[200];
	//fim da cri��o das vari�veis/string
	
	printf("Digite o cpf a ser consultado"); //coletando infrma��es dos usu�rios
	scanf("%s", cpf);//armazena na string
	
	FILE *file; //Entrar na bilbioteca que fala sobre a fun��o file e dentro dela puxar os arquivos
	file = fopen(cpf,"r"); //"r" de read
	
	if(file == NULL) // se a op�ao procurada nao existir
	{
		printf("N�o foi poss�vel abrir o arquivo, n�o localizado!\n");//informando o usu�rio de que a op�ao � nula	
	}
	
	while(fgets(conteudo,200, file) != NULL); //busca as informa��es arquivadas diferentes de nulo
	{
		printf("\n Essas s�o as inform��es do usu�rio\n");//informa 
		printf("%s", conteudo); //apresenta a op��o armazenada na string
		printf("\n\n"); //espa�o
	}
	
	system("pause");// pausa o sistema
		
}

int deletar()
{
		char cpf[40];
		
		printf("Digite o cpf do usu�rio a ser deletado \n");
		scanf("%s",cpf); // s de string
		
		remove(cpf);
		
		FILE *file;//entrar na bilbioteca que fala sobre a fun��o file e dentro dela puxar os arquivos
		file = fopen(cpf, "r");//r de read
		
		if (file == NULL)
		{
			printf("O USU�RIO N�O SE ENCONTRA NO SISTEMA \n");
			system("pause");
		}
		
}



int main ()
{
	int opcao=0; //Definindo as vari�veis
	int laco=1;
	
	for(laco=1;laco=10;)
	{
	
	system("cls");
	 
		setlocale(LC_ALL, "Portuguese"); //Definindo a linguagem
	
		printf("### Cart�rio da EBAC ###\n\n"); //Inicio do menu
		printf("Escolha a op��o desejada do menu: \n\n");
		printf("\t1 - Registrar nomes\n");
		printf("\t2 - Consultar os nomes\n");
		printf("\t3 - Deletar os nomes\n\n");
		printf("Op��o: "); //Fim do menu
	
		scanf("%d", &opcao); //Armazenando a escolha do usu�rio
	
		system("cls");// responsavel por limpar a tela
		
		
		switch(opcao) //inicio da sele��o de menu
		{
			case 1:
			registro();//chamada de fun��es
			break;
			
			case 2: 
			consulta();//chamada de fun��es
			break;
			
			case 3:
			deletar();//chamada de fun��es
			break;
			
	
			
			default:
				printf("essa op�ao n�o est� disponivel\n");
			system("pause");
			break;
				
		}//fim da sele��o
	
		
	}
}
	
io.c…]()
