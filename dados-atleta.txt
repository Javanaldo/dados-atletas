class Atleta{
  constructor(nome,idade,peso,altura,notas){
    this.nome=nome;
    this.idade=idade;
    this.peso=peso;
    this.altura=altura;
    this.notas=notas;
  }
  calculaCategoria(){
    let ca="Categoria: "
    if (this.idade>=9 && this.idade<=11){
      ca=ca+"Infantil"} else{
        if (this.idade==12 ||this.idade==13){
           ca=ca+"Juvenil"}else{
            if(this.idade==14 || this.idade==15){
               ca=ca+"intermediario"}else{
              if (this.idade>=16 && this.idade<=30){
                 ca=ca+"Adulto"}else{
                   ca=ca+"Sem Categoria"
                }//fecha else
              }//fecha else
          }//fecha else
      }//fecha else
    console.log(ca)
  }//} fecha calculaCategoria
  calculaIMC(){
    let imc_a ="";
    imc_a ="IMC: "+(this.peso/(this.altura*this.altura));
    console.log(imc_a)
  }
  calculaMediaValida(){
    this.notas= this.notas.sort(comparar)// só o método sort não ordenava corretamente, então pesquisei um algoritmo de comparação
    this.notas = this.notas.slice(1,4);// Elimina a nota mais alta e a mais baixa
    let total=0;
  this.notas.forEach(function(somar){// soma as notas válidas
    total=total+somar
  });
  let media = total/(this.notas.length)// calcula a média
  console.log("Média: "+media)
  }//} fecha calculaMediaValida
  obtemNomeAtleta(){
    console.log("Nome: "+this.nome);
  }// fecha obtemNome
obtemIdadeAtleta(){
  console.log("Idade: "+this.idade);
}//fecha obtemIdadeAtleta()  
obtemPesoAtleta(){
  console.log("Peso: "+this.peso);
}// fecha obtemPesoAtleta()
obtemNotasAtleta(){
  console.log("Notas: "+this.notas);
}// fecha obtemNotasAtleta()
obtemAltura(){
  console.log("Altura: "+this.altura);
}//fecha obtemAltura
}
// Declara o atleta
const atleta = new Atleta("Cesar Abascal",
    30, 80, 1.70,
    [10, 9.34, 8.42, 10, 7.88]);
function comparar(a,b){// compara os numeros para ter certeza que sort funcione adequadamente;
  return a-b;
}// fecha comparar
//as linhas abaixo mostram as informações sobre o atleta
atleta.obtemNomeAtleta();
atleta.obtemIdadeAtleta();
atleta.obtemPesoAtleta();
atleta.obtemAltura();
atleta.obtemNotasAtleta();
atleta.calculaCategoria();
atleta.calculaIMC();
atleta.calculaMediaValida();