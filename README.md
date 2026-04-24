
--- FAVOR TIRAR O CÓDGIO. COLOQUE NA PASTA ATIVIDADE 01 --

Alunos: Adnei Wesley, Rafael Glória.

import React, { useState } from 'react';
import { View, Text, Button, TextInput, StyleSheet, Alert } from 'react-native';

const App = () => {
  const [personalMessage, setPersonalMessage] = useState('');
  const [motivation, setMotivation] = useState('Keep pushing forward!');

  const changeMessage = () => {
    const messages = [
      "Acredite em si mesmo!",
      "Você está indo bem!",
      "O sucesso está a caminho!",
      "Nunca desista!",
      "A persistência é a chave!",
      "Você é capaz!",
    ];
    const randomIndex = Math.floor(Math.random() * messages.length);
    setMotivation(messages[randomIndex]);
  };

  const showAlert = () => {
    Alert.alert("Sua Mensagem", personalMessage ? personalMessage : "Nenhuma mensagem digitada!");
  };

  return (
    <View style={styles.container}>
      <Text style={styles.title}>👤 Wesley</Text>
      <Text style={styles.course}>📚 Curso: Informática</Text>
      
      <View style={styles.motivationBox}>
        <Text style={styles.motivation}>"{motivation}"</Text>
      </View>

      <TextInput
        style={styles.input}
        placeholder="Digite sua mensagem personalizada..."
        placeholderTextColor="#999"
        value={personalMessage}
        onChangeText={setPersonalMessage}
      />

      <View style={styles.buttonsContainer}>
        <Button 
          title="Mudar Mensagem" 
          onPress={changeMessage}
          color="#4CAF50"
        />
        <View style={styles.buttonSpace} />
        <Button 
          title="Mostrar Alerta" 
          onPress={showAlert}
          color="#2196F3"
        />
      </View>

      {personalMessage !== '' && (
        <Text style={styles.personalized}>
          Sua mensagem: {personalMessage}
        </Text>
      )}
    </View>
  );
};

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#e0f7fa',
    padding: 20,
  },
  title: {
    fontSize: 28,
    fontWeight: 'bold',
    color: '#333',
    marginBottom: 10,
  },
  course: {
    fontSize: 18,
    color: '#555',
    marginBottom: 20,
  },
  motivationBox: {
    backgroundColor: '#fff',
    padding: 15,
    borderRadius: 10,
    marginBottom: 25,
    borderLeftWidth: 4,
    borderLeftColor: '#4CAF50',
  },
  motivation: {
    fontSize: 16,
    fontStyle: 'italic',
    color: '#333',
    textAlign: 'center',
  },
  input: {
    height: 45,
    borderColor: '#4CAF50',
    borderWidth: 2,
    marginBottom: 20,
    width: '100%',
    paddingHorizontal: 15,
    borderRadius: 8,
    backgroundColor: '#fff',
    fontSize: 16,
  },
  buttonsContainer: {
    width: '100%',
    marginBottom: 20,
  },
  buttonSpace: {
    height: 10,
  },
  personalized: {
    fontSize: 14,
    color: '#2196F3',
    marginTop: 10,
    fontWeight: '500',
  },
});

export default App;
