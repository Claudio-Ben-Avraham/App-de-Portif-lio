# Projeto: App Pessoal com React Native

Este projeto consiste em criar um aplicativo mobile com **duas telas** utilizando React Native, onde aplicamos componentes, estilização e navegação para exibir informações pessoais e habilidades.

---

## Objetivos de Aprendizagem

Ao concluir este projeto, você será capaz de:

- Criar e organizar **componentes** reutilizáveis em React Native.
- Aplicar **estilização** com StyleSheet e conceitos de Flexbox.
- Implementar **navegação entre telas** usando a estratégia de sua escolha (Stack, Drawer ou Tab Navigation).
- Estruturar dados de forma clara e visualmente agradável.
- Documentar e organizar um projeto React Native para exposição e versionamento no GitHub.

---

## Estrutura do Projeto

AppPessoal/
│
├── App.js
├── package.json
├── assets/
│ └── suaFoto.jpg
├── screens/
│ ├── MainScreen.js
│ └── SkillScreen.js
└── components/
└── SkillItem.js


---

## Funcionalidades

### Main Screen

- Exibe sua foto e seu nome.
- Lista links importantes para contato ou portfólio, como:
  - LinkedIn
  - GitHub
  - Email
- Componentes principais: `View`, `Text`, `Image`, `TouchableOpacity` para os links.

### Skill Screen

- Exibe sua foto e seu nome.
- Mostra sua **árvore de habilidades** e nível de cada uma, podendo ser representada com:
  - Barras de progresso
  - Ícones ou textos
- Componentes principais: `View`, `Text`, `Image`, componentes customizados como `SkillItem`.

---

## Navegação

- Utilizamos a biblioteca **React Navigation** para gerenciar a navegação entre as telas.
- Exemplo com **Stack Navigation**:
  ```javascript
  import { NavigationContainer } from '@react-navigation/native';
  import { createNativeStackNavigator } from '@react-navigation/native-stack';
  import MainScreen from './screens/MainScreen';
  import SkillScreen from './screens/SkillScreen';

  const Stack = createNativeStackNavigator();

  export default function App() {
    return (
      <NavigationContainer>
        <Stack.Navigator initialRouteName="Main">
          <Stack.Screen name="Main" component={MainScreen} />
          <Stack.Screen name="Skills" component={SkillScreen} />
        </Stack.Navigator>
      </NavigationContainer>
    );
  }

Estilização

    Utilizamos StyleSheet para criar estilos consistentes.

    Exemplos de propriedades aplicadas:

        flex, flexDirection, justifyContent, alignItems

        margin, padding, borderRadius

        fontSize, color, fontWeight

Componentes Reutilizáveis

    SkillItem: Componente que representa uma habilidade com nome e nível.

    import React from 'react';
    import { View, Text, StyleSheet } from 'react-native';

    const SkillItem = ({ skill, level }) => (
      <View style={styles.container}>
        <Text style={styles.skill}>{skill}</Text>
        <Text style={styles.level}>{level}</Text>
      </View>
    );

    const styles = StyleSheet.create({
      container: { flexDirection: 'row', justifyContent: 'space-between', marginVertical: 5 },
      skill: { fontWeight: 'bold' },
      level: { color: 'gray' },
    });

    export default SkillItem;

Tecnologias Utilizadas

    React Native: Framework para desenvolvimento mobile.

    React Navigation: Biblioteca de navegação.

    JavaScript / JSX: Linguagem base e sintaxe de componentes.

    StyleSheet / Flexbox: Para estilização responsiva.

Conclusão

Este projeto demonstra como criar um app pessoal interativo e responsivo com React Native, utilizando boas práticas de:

    Componentização

    Estilização

    Navegação

    Organização de arquivos e dados

Pode ser facilmente expandido com animações, links externos clicáveis e integração com APIs.
