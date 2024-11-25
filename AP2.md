```cpp
from abc import ABC, abstractmethod
from typing import Any

class ModeloRelatorio(ABC):
    def __init__(self):
        self._dados_relatorio = None
    
    def gerar_relatorio(self):
        """
        Método template que define o esqueleto do processo de geração de relatório.
        Chama os métodos de adição de cabeçalho, corpo e rodapé em uma sequência fixa.
        """
        self._adicionar_cabecalho()
        self._adicionar_corpo()
        self._adicionar_rodape()
    
    def _adicionar_cabecalho(self):
        """
        Método padrão para adicionar o cabeçalho do relatório.
        Pode ser sobrescrito por subclasses, se necessário.
        """
        print("Cabeçalho: Relatório Padrão")
    
    @abstractmethod
    def _adicionar_corpo(self):
        """
        Método abstrato que deve ser implementado pelas subclasses.
        Representa a parte principal e específica do relatório.
        """
        pass
    
    def _adicionar_rodape(self):
        """
        Método padrão para adicionar o rodapé do relatório.
        Pode ser sobrescrito por subclasses, se necessário.
        """
        print("Rodapé: Fim do Relatório")
    
    def definir_dados_relatorio(self, dados: Any):
        """
        Define os dados que serão utilizados na geração do relatório.
        
        Args:
            dados (Any): Dados do relatório de qualquer tipo.
        """
        self._dados_relatorio = dados
        print(f"Dados do Relatório: {self._dados_relatorio}")

class RelatorioFinanceiro(ModeloRelatorio):
    def _adicionar_corpo(self):
        """
        Implementação específica do corpo para relatórios financeiros.
        """
        print(f"Corpo: Dados financeiros detalhados... {self._dados_relatorio}")

class RelatorioRH(ModeloRelatorio):
    def _adicionar_corpo(self):
        """
        Implementação específica do corpo para relatórios de RH.
        """
        print(f"Corpo: Dados de RH... {self._dados_relatorio}")

# Exemplo de uso
def main():
    # Criando e gerando relatório financeiro
    relatorio_financeiro = RelatorioFinanceiro()
    relatorio_financeiro.definir_dados_relatorio("Relatório de Vendas 2024")
    relatorio_financeiro.gerar_relatorio()

    print("\n")

    # Criando e gerando relatório de RH
    relatorio_rh = RelatorioRH()
    relatorio_rh.definir_dados_relatorio("Relatório de Colaboradores - Outubro")
    relatorio_rh.gerar_relatorio()

# Executa o código apenas se for o script principal
if __name__ == "__main__":
    main()
```
