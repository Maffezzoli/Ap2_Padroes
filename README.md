# 📋 Template Method: Trabalho de Padrões de Projeto

## 🚀 Apresentação do Padrão de Projeto

O Template Method é um padrão comportamental que define o esqueleto de um algoritmo na superclasse, permitindo que subclasses substituam etapas específicas sem alterar a estrutura geral do algoritmo.

## 👥 Autores
- Rodrigo Lima
- Daniel Maffezzoli

## 📚 Conteúdo da Apresentação

### 1. Identificação do Padrão
- **Tipo**: Padrão Comportamental
- **Objetivo**: Definir o esqueleto de um algoritmo em uma classe base, permitindo que subclasses implementem comportamentos específicos

### 2. Problema Endereçado
- Algoritmos com estruturas similares mas implementações variadas
- Código duplicado e de difícil manutenção
- Necessidade de flexibilidade e extensibilidade

### 3. Solução Proposta
- Criação de uma classe abstrata com método template
- Definição de pontos de extensão
- Implementação de métodos concretos e abstratos

### 4. Exemplo de Código
```python
from abc import ABC, abstractmethod

class ModeloRelatorio(ABC):
    def gerar_relatorio(self):
        self._adicionar_cabecalho()
        self._adicionar_corpo()
        self._adicionar_rodape()
    
    @abstractmethod
    def _adicionar_corpo(self):
        pass

class RelatorioFinanceiro(ModeloRelatorio):
    def _adicionar_corpo(self):
        print("Dados financeiros detalhados")
```

### 5. Vantagens e Desvantagens

#### Vantagens ✅
- Reutilização de código
- Flexibilidade de implementação
- Padronização de algoritmos

#### Desvantagens ❌
- Possível aumento de complexidade
- Limitações de personalização
- Potencial violação de princípios de design

## 🛠️ Tecnologias Utilizadas
- Python
- Programação Orientada a Objetos
- Padrões de Projeto

## 📄 Licença
Este projeto é licenciado sob a Licença MIT.

## 🤝 Contribuições
Contribuições são bem-vindas! Por favor, leia as diretrizes de contribuição antes de enviar um pull request.

---

<div align="center">
📌 Trabalho de Padrões de Projeto - 2024
</div>
