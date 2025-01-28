// App.js
import React, { useState } from 'react';
import { Box, Button, Flex, Heading, VStack, HStack, Text, Input } from '@chakra-ui/react';

const verbs = [
  { present: 'Open', past: 'Opened', pastParticiple: 'Opened', spanish: 'Abrir' },
  { present: 'Accept', past: 'Accepted', pastParticiple: 'Accepted', spanish: 'Aceptar' },
  { present: 'Love', past: 'Loved', pastParticiple: 'Loved', spanish: 'Amar' },
  { present: 'Appear', past: 'Appeared', pastParticiple: 'Appeared', spanish: 'Aparecer' },
  { present: 'Learn', past: 'Learned', pastParticiple: 'Learned', spanish: 'Aprender' },
  { present: 'Help', past: 'Helped', pastParticiple: 'Helped', spanish: 'Ayudar' },
  { present: 'Dance', past: 'Danced', pastParticiple: 'Danced', spanish: 'Bailar' },
  { present: 'Drink', past: 'Drank', pastParticiple: 'Drunk', spanish: 'Beber' },
  { present: 'Fall', past: 'Fell', pastParticiple: 'Fallen', spanish: 'Caer' },
  { present: 'Change', past: 'Changed', pastParticiple: 'Changed', spanish: 'Cambiar' },
  { present: 'Walk', past: 'Walked', pastParticiple: 'Walked', spanish: 'Caminar' },
  { present: 'Sing', past: 'Sang', pastParticiple: 'Sung', spanish: 'Cantar' },
  { present: 'Close', past: 'Closed', pastParticiple: 'Closed', spanish: 'Cerrar' },
  { present: 'Cook', past: 'Cooked', pastParticiple: 'Cooked', spanish: 'Cocinar' },
  { present: 'Start', past: 'Started', pastParticiple: 'Started', spanish: 'Comenzar' },
  { present: 'Eat', past: 'Ate', pastParticiple: 'Eaten', spanish: 'Comer' },
  { present: 'Buy', past: 'Bought', pastParticiple: 'Bought', spanish: 'Comprar' },
  { present: 'Drive', past: 'Drove', pastParticiple: 'Driven', spanish: 'Conducir' },
  { present: 'Meet', past: 'Met', pastParticiple: 'Met', spanish: 'Conocer' },
  { present: 'Get', past: 'Got', pastParticiple: 'Gotten', spanish: 'Conseguir' },
  { present: 'Build', past: 'Built', pastParticiple: 'Built', spanish: 'Construir' },
  { present: 'Count', past: 'Counted', pastParticiple: 'Counted', spanish: 'Contar' },
  { present: 'Run', past: 'Ran', pastParticiple: 'Run', spanish: 'Correr' },
  { present: 'Cut', past: 'Cut', pastParticiple: 'Cut', spanish: 'Cortar' },
  { present: 'Grow', past: 'Grew', pastParticiple: 'Grown', spanish: 'Crecer' },
  { present: 'Believe', past: 'Believed', pastParticiple: 'Believed', spanish: 'Creer' },
  { present: 'Give', past: 'Gave', pastParticiple: 'Given', spanish: 'Dar' },
  { present: 'Say', past: 'Said', pastParticiple: 'Said', spanish: 'Decir' },
  { present: 'Tell', past: 'Told', pastParticiple: 'Told', spanish: 'Decir' },
  { present: 'Leave', past: 'Left', pastParticiple: 'Left', spanish: 'Dejar' },
  { present: 'Draw', past: 'Drew', pastParticiple: 'Drawn', spanish: 'Dibujar' },
  { present: 'Enjoy', past: 'Enjoyed', pastParticiple: 'Enjoyed', spanish: 'Disfrutar' },
  { present: 'Sleep', past: 'Slept', pastParticiple: 'Slept', spanish: 'Dormir' },
  { present: 'Choose', past: 'Chose', pastParticiple: 'Chosen', spanish: 'Elegir' },
  { present: 'Begin', past: 'Began', pastParticiple: 'Begun', spanish: 'Empezar' },
  { present: 'Find', past: 'Found', pastParticiple: 'Found', spanish: 'Encontrar' },
  { present: 'Teach', past: 'Taught', pastParticiple: 'Taught', spanish: 'Enseñar' },
  { present: 'Understand', past: 'Understood', pastParticiple: 'Understood', spanish: 'Entender' },
  { present: 'Send', past: 'Sent', pastParticiple: 'Sent', spanish: 'Enviar' },
  { present: 'Write', past: 'Wrote', pastParticiple: 'Written', spanish: 'Escribir' },
  { present: 'Listen', past: 'Listened', pastParticiple: 'Listened', spanish: 'Escuchar' },
  { present: 'Hope', past: 'Hoped', pastParticiple: 'Hoped', spanish: 'Esperar' },
  { present: 'Wait', past: 'Waited', pastParticiple: 'Waited', spanish: 'Esperar' },
  { present: 'Stand', past: 'Stood', pastParticiple: 'Stood', spanish: 'Estar de pie' },
  { present: 'Study', past: 'Studied', pastParticiple: 'Studied', spanish: 'Estudiar' },
  { present: 'Explain', past: 'Explained', pastParticiple: 'Explained', spanish: 'Explicar' },
  { present: 'Win', past: 'Won', pastParticiple: 'Won', spanish: 'Ganar' },
  { present: 'Spend', past: 'Spent', pastParticiple: 'Spent', spanish: 'Gastar' },
  { present: 'Turn', past: 'Turned', pastParticiple: 'Turned', spanish: 'Girar' },
  { present: 'Like', past: 'Liked', pastParticiple: 'Liked', spanish: 'Gustar' },
  { present: 'Speak', past: 'Spoke', pastParticiple: 'Spoken', spanish: 'Hablar' },
  { present: 'Talk', past: 'Talked', pastParticiple: 'Talked', spanish: 'Hablar' },
  { present: 'Do', past: 'Did', pastParticiple: 'Done', spanish: 'Hacer' },
  { present: 'Make', past: 'Made', pastParticiple: 'Made', spanish: 'Hacer' },
  { present: 'Try', past: 'Tried', pastParticiple: 'Tried', spanish: 'Intentar' },
  { present: 'Invite', past: 'Invited', pastParticiple: 'Invited', spanish: 'Invitar' },
  { present: 'Go', past: 'Went', pastParticiple: 'Gone', spanish: 'Ir' },
  { present: 'Play', past: 'Played', pastParticiple: 'Played', spanish: 'Jugar' },
  { present: 'Read', past: 'Read', pastParticiple: 'Read', spanish: 'Leer' },
  { present: 'Call', past: 'Called', pastParticiple: 'Called', spanish: 'Llamar' },
  { present: 'Wear', past: 'Wore', pastParticiple: 'Worn', spanish: 'Llevar' },
  { present: 'Cry', past: 'Cried', pastParticiple: 'Cried', spanish: 'Llorar' },
  { present: 'Keep', past: 'Kept', pastParticiple: 'Kept', spanish: 'Mantener' },
  { present: 'Look', past: 'Looked', pastParticiple: 'Looked', spanish: 'Mirar' },
  { present: 'Die', past: 'Died', pastParticiple: 'Died', spanish: 'Morir' },
  { present: 'Show', past: 'Showed', pastParticiple: 'Shown', spanish: 'Mostrar' },
  { present: 'Move', past: 'Moved', pastParticiple: 'Moved', spanish: 'Mover' },
  { present: 'Need', past: 'Needed', pastParticiple: 'Needed', spanish: 'Necesitar' },
  { present: 'Offer', past: 'Offered', pastParticiple: 'Offered', spanish: 'Ofrecer' },
  { present: 'Hear', past: 'Heard', pastParticiple: 'Heard', spanish: 'Oír' },
  { present: 'Forget', past: 'Forgot', pastParticiple: 'Forgotten', spanish: 'Olvidar' },
  { present: 'Order', past: 'Ordered', pastParticiple: 'Ordered', spanish: 'Ordenar' },
  { present: 'Pay', past: 'Paid', pastParticiple: 'Paid', spanish: 'Pagar' },
  { present: 'Stop', past: 'Stopped', pastParticiple: 'Stopped', spanish: 'Parar' },
  { present: 'Think', past: 'Thought', pastParticiple: 'Thought', spanish: 'Pensar' },
  { present: 'Lose', past: 'Lost', pastParticiple: 'Lost', spanish: 'Perder' },
  { present: 'Allow', past: 'Allowed', pastParticiple: 'Allowed', spanish: 'Permitir' },
  { present: 'Let', past: 'Let', pastParticiple: 'Let', spanish: 'Permitir' },
  { present: 'Plan', past: 'Planned', pastParticiple: 'Planned', spanish: 'Planear' },
  { present: 'Put', past: 'Put', pastParticiple: 'Put', spanish: 'Poner' },
  { present: 'Ask', past: 'Asked', pastParticiple: 'Asked', spanish: 'Preguntar' },
  { present: 'Stay', past: 'Stayed', pastParticiple: 'Stayed', spanish: 'Quedarse' },
  { present: 'Want', past: 'Wanted', pastParticiple: 'Wanted', spanish: 'Querer' },
  { present: 'Break', past: 'Broke', pastParticiple: 'Broken', spanish: 'Romper' },
  { present: 'Know', past: 'Knew', pastParticiple: 'Known', spanish: 'Saber' },
  { present: 'Jump', past: 'Jumped', pastParticiple: 'Jumped', spanish: 'Saltar' },
  { present: 'Follow', past: 'Followed', pastParticiple: 'Followed', spanish: 'Seguir' },
  { present: 'Sit', past: 'Sat', pastParticiple: 'Sat', spanish: 'Sentarse' },
  { present: 'Feel', past: 'Felt', pastParticiple: 'Felt', spanish: 'Sentir' },
  { present: 'Mean', past: 'Meant', pastParticiple: 'Meant', spanish: 'Significar' },
  { present: 'Have', past: 'Had', pastParticiple: 'Had', spanish: 'Tener' },
  { present: 'Finish', past: 'Finished', pastParticiple: 'Finished', spanish: 'Terminar' },
  { present: 'Take', past: 'Took', pastParticiple: 'Taken', spanish: 'Tomar' },
  { present: 'Work', past: 'Worked', pastParticiple: 'Worked', spanish: 'Trabajar' },
  { present: 'Use', past: 'Used', pastParticiple: 'Used', spanish: 'Usar' },
  { present: 'Sell', past: 'Sold', pastParticiple: 'Sold', spanish: 'Vender' },
  { present: 'Come', past: 'Came', pastParticiple: 'Come', spanish: 'Venir' },
  { present: 'See', past: 'Saw', pastParticiple: 'Seen', spanish: 'Ver' },
  { present: 'Watch', past: 'Watched', pastParticiple: 'Watched', spanish: 'Ver' },
  { present: 'Travel', past: 'Traveled', pastParticiple: 'Traveled', spanish: 'Viajar' },
  { present: 'Visit', past: 'Visited', pastParticiple: 'Visited', spanish: 'Visitar' },
  { present: 'Live', past: 'Lived', pastParticiple: 'Lived', spanish: 'Vivir' },
  { present: 'Ride', past: 'Rode', pastParticiple: 'Ridden', spanish: 'Montar/andar' }
];

const VerbCard = ({ verb }) => {
  const [displayForm, setDisplayForm] = useState('present');

  // Display the current form based on the value of `displayForm` state
  const currentText = verb[displayForm] || 'N/A';

  // Define background colors for each form
  const getBgColor = () => {
    switch (displayForm) {
      case 'present':
        return 'blue.100'; // Light blue for present
      case 'past':
        return 'orange.100'; // Light orange for past
      case 'pastParticiple':
        return 'green.100'; // Light green for past participle
      case 'spanish':
        return 'yellow.100'; // Light yellow for Spanish
      default:
        return 'gray.100'; // Default background color
    }
  };

  return (
    <Box
      borderWidth="1px"
      borderRadius="lg"
      padding="4"
      margin="2"
      width="180px"
      textAlign="center"
      bg={getBgColor()} // Set background color based on conjugation form
      boxShadow="md"
    >
      <Text fontSize="xl" fontWeight="bold" color="black" mb="4">
        {currentText}
      </Text>
      <VStack spacing="2" justify="center">
        <Button colorScheme="blue" size="sm" onClick={() => setDisplayForm('present')}>
          Present
        </Button>
        <Button colorScheme="orange" size="sm" onClick={() => setDisplayForm('past')}>
          Past
        </Button>
        <Button colorScheme="green" size="sm" onClick={() => setDisplayForm('pastParticiple')}>
          Past Participle
        </Button>
        <Button colorScheme="yellow" size="sm" onClick={() => setDisplayForm('spanish')}>
          Español
        </Button>
      </VStack>
    </Box>
  );
};

const App = () => {
  const [searchQuery, setSearchQuery] = useState('');

  // Filter the verbs based on the search query
  const filteredVerbs = verbs.filter(verb => {
    const searchLowerCase = searchQuery.toLowerCase();
    return (
      verb.present.toLowerCase().includes(searchLowerCase) ||
      verb.past.toLowerCase().includes(searchLowerCase) ||
      verb.pastParticiple.toLowerCase().includes(searchLowerCase) ||
      verb.spanish.toLowerCase().includes(searchLowerCase)
    );
  });

  return (
    <VStack spacing="6" padding="4">
      <Heading>Verb Conjugation Cards</Heading>
      
      {/* Search input */}
      <Input
        placeholder="Search verbs..."
        value={searchQuery}
        onChange={(e) => setSearchQuery(e.target.value)}
        size="lg"
        mb="4"
      />

      {/* Display the filtered verbs */}
      <Flex wrap="wrap" justify="center">
        {filteredVerbs.map((verb, index) => (
          <VerbCard key={index} verb={verb} />
        ))}
      </Flex>
    </VStack>
  );
};

export default App;