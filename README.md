# Nietzschean-Prose-Generation-with-LSTM-Networks
This project implements a character-level recurrent neural network (RNN) to generate text that mimics the philosophical style of Friedrich Nietzsche. By training on a corpus of his work, the model learns not just vocabulary, but the structural patterns, punctuation, and "tone" of the author.

🧠 Technical ArchitectureThe model is built using Keras and TensorFlow with the following pipeline:Data Processing: The raw text (600,893 characters) is converted to lowercase and tokenized at the character level.

Sequence Vectorization: Text is broken into overlapping segments of 60 characters with a stride of 3. These are one-hot encoded into a 3D boolean array of shape $(200278, 60, 57)$.

The Neural Network:LSTM Layer: 128 units to capture long-term dependencies in prose.Dense Layer: A Softmax-activated layer with 57 units (the size of the character vocabulary) to predict the probability of the next character.

Optimization: Trained using the RMSprop optimizer with a categorical cross-entropy loss function.

🌡️ Key Experiment: Softmax TemperatureA critical component of this project is the implementation of a sampling function with a temperature parameter.
This allows us to control the "creativity" of the model:

Low Temperature: Makes the model confident but repetitive (chooses only the highest probability characters).
High Temperature: Increases diversity but introduces more spelling errors and structural chaos.


📊 Results & OutputAfter 15 epochs, the model achieved a loss of 1.33.Example of Generated Text:
"immediately disclose what it really is--namely, a will to the the believest constive the art of the persision the says of a gan himself need not religion a consting be naturing and suld the pretendents..." 

🛠️ DependenciesPython 3.xKeras / TensorFlowNumPyMatplotlib (for probability distribution visualization)
