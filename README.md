#include <iostream>//Inclui a biblioteca padrão de entrada e saída em C++,necessário para usar cin e cout
 #include <cstdlib>//Inclui a biblioteca padrão C,que permite o uso da função rand()para geração de número aleatório
 
 using namespace std;//permite o uso direto das funções e objetos do namespace std,como cout e cin,sem precisar prefixar com std::
 
int main(){//função principal onde a execução do programa começa.
 
     //Gera um número aleatório entre 1 e 100
     //rand() % 100 gera um número entre 0 e 99.Adicionando 1,temos o intervalo de 1 a 100.
     int numeroSecreto=rand()% 100 +1;
     
     int tentativas=8;//Define o número maxímo de tentativas que o usuário tem para adivinhar o número
     int palpite;//Declara uma variável para armazenar o palpite de usúario.
     
     do{//Início de um loop do-while que continuará executando enquanto a condição do while for verdadeiro.
     {
       //Exibe o número da tentativa atual e solicita ao usuário que insira um número.
        cout << "tentativa" << tentativas <<":Digite um número";
       
        cin >> palpite;//le o palpite do usuário e armazena na variável palpite.
        
        //Verifica se o palpite é correto
        if (palpite <numeroSecreto)
        {
            cout <<"Muito baixo!" <<endl;//Informa ao usuário que o palpite é muito baixo.
            
            //Verifica se o palpite do usuário é maior que o número secreto.
        }else if (palpite>numeroSecreto)
        
            cout <<"Muito alto!" <<endl;//Informa ao usuário que o palpite é Muito alto
            
        }tentativas--;//Decrementa o número de tentativas restantes.
} while (palpite != numeroSecreto&& tentativas>0);//Continua o loop enquanto o palpite não for o número secreto e houver tentativas restantes

//Após sair do loop,Verifica se o usuário adivinhou o número secreto.
if(palpite==numeroSecreto)
{
    //Informa ao usuário que ele acertou o número secreto e mostra quantas tentativas foram usadas.
    //Note que a variável tentativas aqui reflete as tentativas restantes.Para mostrar quantas tentativas foram usadas,usamos 8 - tentativas.
    cout<<"Parabéns!Voce acertou o número em "<< tentativas<<"tentativas!"<<endl;
}
else
{
    //Informa ao usuário que ele não conseguiu adivinhar o número e revela qual era o número secreto.
cout<<"Voce não conseguiu adivinhar o número.O número secreto era"<<numeroSecreto<<"!"<< endl;
}
return 0;// Retorna 0 indicando que o programa terminou com sucesso.
}
