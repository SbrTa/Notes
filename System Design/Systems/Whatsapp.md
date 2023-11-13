# Whatsapp System Design

#### Key insights
  - 📱 Whatsapp's key features, such as group messaging and read receipts, are highly sought after in a chat-based application design interview.
  - 📸 Image and video sharing is a crucial feature in messaging systems like WhatsApp.
  - 📚 The system design playlist provides valuable information on topics such as load balancing and messaging queues for implementing chat messaging systems.
  - 💬 Single point of failure is a crucial consideration in the WhatsApp system design, highlighting the importance of ensuring reliability and availability for users.
  - 🌐 Websockets enable peer-to-peer communication, eliminating the need for client-server semantics and allowing the server to directly send messages to the client.
  - 🔁 The system can store messages in a database and retry sending them until User B receives them, ensuring persistence and reliability.
  - 🔄 The message flow in the system involves multiple gateways and session services to ensure the message is successfully delivered and acknowledged.
  - 🗺️ Consistent hashing helps reduce memory footprint across servers by delegating only some information to specific boxes, improving efficiency in the Whatsapp chat messaging system.


#### Q&A
  - What are the key features of chat-based applications like WhatsApp?
    - Chat-based applications like WhatsApp have key features such as group messaging, read receipts, load balancing, and message queues.
  - How are messages stored in WhatsApp?
    - WhatsApp chats are temporary and stored only on users' devices, but for compliance or official communication, messages need to be stored permanently.
  - How does WhatsApp handle group messaging?
    - WhatsApp handles group messaging by decoupling the information of group members in a group service, allowing the session service to retrieve the user connections and determine which gateway they are connected to.
  - What is the role of the gateway service in WhatsApp architecture?
    - The gateway service in WhatsApp architecture allows users to connect to the cloud and send messages to other users, eliminating the need for extensive security measures on the internal services.
  - How does WhatsApp ensure message delivery and receipt confirmation?
    - WhatsApp ensures message delivery and receipt confirmation by sending and receiving delivery receipts when a user opens a chat tab and sends a message, ensuring that the sender is notified.


#### Timestamped Summary
  - 📱 00:00 Designing a chat-based application like WhatsApp involves considering key features such as group messaging and read receipts, gradually adding more based on the interviewer's response, and implementing concepts like load balancing and messaging queues.
  - 📱 03:24 The Whatsapp architecture uses a gateway to connect users to the cloud and send messages, eliminating the need for extensive security measures, and storing user connections as a simple TCP connection to avoid duplication and cost.
  - 📱 05:46 The Whatsapp system uses multiple servers to avoid single point of failure, uses websockets for real-time communication, and ensures message delivery and receipt notifications for users.
  - 📝 11:02 The server logs user activity to determine if a user is online, updating a table with the timestamp, while a microservice tracks user activity to update the last seen tag; the client distinguishes between user activities and app messages when sending requests to the last seen service.
  - 📱 14:20 The core function of WhatsApp is sending messages, with group messaging facilitated by decoupling group member information and using a session service to determine user connections and gateways.
  - 📱 17:17 The architecture of the chat messaging system involves routing messages, limiting group sizes, and using separate session services to reduce memory usage, while also using a parser microservice to send and convert messages for efficient delivery.
  - 📱 20:42 Consistent hashing reduces duplication and memory usage in WhatsApp by delegating information to specific servers, while message queues ensure reliable message delivery and client notification of failures, but group receipts are expensive due to the need for confirmation from everyone.
  - 📝 22:57 Facebook Messenger prioritizes message delivery and acknowledgement over features like last seen during high load events to maintain system health and performance.

#### Source
  - https://www.youtube.com/watch?v=vvhC64hQZMk&ab_channel=GauravSen
  - https://www.youtube.com/watch?v=xyLO8ZAk2KE&ab_channel=ByteMonk


![image](https://github.com/SbrTa/Notes/assets/8649145/832f711a-4af8-4f5a-9540-4a41afc49b40)
