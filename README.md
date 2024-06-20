import React, { useState } from "react";
import { Text, View, Button, StyleSheet } from "react-native";

export default function App() {
  const [events, setEvents] = useState([]);

  const fetchEvents = () => {
    // Placeholder for mock events
    const mockEvents = [
      { id: 1, title: "Meeting with Client A" },
      { id: 2, title: "Team Standup Meeting" },
      { id: 3, title: "Project Deadline" }
    ];
    setEvents(mockEvents);
  };

  return (
    <View style={styles.container}>
      <Button title="Fetch Calendar Events" onPress={fetchEvents} />
      {events.map((event) => (
        <Text key={event.id}>{event.title}</Text>
      ))}
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
    padding: 20
  }
});
