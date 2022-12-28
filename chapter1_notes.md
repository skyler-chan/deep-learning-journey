# Notes from Fast AI course

**\*\***\*\***\*\***Tasks that use Deep Learning**\*\***\*\***\*\***

- Natural language processing (NLP):: Answering questions; speech recognition; summarizing documents; classifying documents; finding names, dates, etc. in documents; searching for articles mentioning a concept
- Computer vision:: Satellite and drone imagery interpretation (e.g., for disaster resilience); face recognition; image captioning; reading traffic signs; locating pedestrians and vehicles in autonomous vehicles
- Medicine:: Finding anomalies in radiology images, including CT, MRI, and X-ray images; counting features in pathology slides; measuring features in ultrasounds; diagnosing diabetic retinopathy
- Biology:: Folding proteins; classifying proteins; many genomics tasks, such as tumor-normal sequencing and classifying clinically actionable genetic mutations; cell classification; analyzing protein/protein interactions
- Image generation:: Colorizing images; increasing image resolution; removing noise from images; converting images to art in the style of famous artists
- Recommendation systems:: Web search; product recommendations; home page layout
- Playing games:: Chess, Go, most Atari video games, and many real-time strategy games
- Robotics:: Handling objects that are challenging to locate (e.g., transparent, shiny, lacking texture) or hard to pick up
- Other applications:: Financial and logistical forecasting, text to speech, and much more...

# History of Neural Networks

- Warren McCulloch + Walter Pitts created a math model for an artif neuron, called threshold logic

- Perceptron: can recognize simple shapes

- Parallel Distributed Processing (PDP), requires:

1. Set of processing units
2. State of activation
3. Output f(x) for each unit
4. Pattern of connectivity among units
5. Propagation rule for patterns thru network of connectivities
6. Activation rule for combining inputs impinging on a unit, w current state of unit product an output for it
7. Learning rule - patterns of connectivity modified by experience
8. Environment - that system must operate within

# How to learn DL

- Read content/textbook/writing, watch lecture videos while following along with Jupyter notebooks
- Learn through examples, then figure out how it works underneath
- Use DL to solve own problems
- Techniques >> caring about which software/library to use

# Glossary

GPU: Graphics Processing Unit/graphics card

- Handle thousands of single tasks at same time
- GPUs run NNs 100x > regular CPUs

Jupyter Notebook:

- Piece of software with formatted text, code, images, videos, all in an interactive document

Full vs Stripped Notebooks:

- Full: with prose/outputs
- Stripped: without prose/ouputs

# Building our first model - Dog vs Cat Classifier

## How?

1. Download a dataset of dog, cat photos
2. Train a model using dataset (bunch of images, emails, sounds - any data)
