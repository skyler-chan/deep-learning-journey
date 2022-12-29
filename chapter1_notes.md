# Notes from Chapter 1 Fast AI Course

# Sources

1. Main site: https://course.fast.ai/Lessons/lesson1.html#resources
2. Video: https://www.youtube.com/watch?v=8SF_h3xF3cE

Summary of Chapter 1 (according to ChatGPT):

Chapter 1 of the Fast AI Practical Deep Learning course introduces the concept of deep learning and how it can be applied to various fields such as computer vision, natural language processing, and speech recognition. The chapter covers the basics of neural networks, including how they are composed of layers of interconnected nodes and how they can be trained using large amounts of data and an optimization algorithm. The chapter also introduces the concept of overfitting, which is when a model performs well on the training data but poorly on new, unseen data, and ways to prevent it such as using regularization techniques. Finally, the chapter provides an overview of the tools and libraries that will be used in the course, including Python, PyTorch, and Jupyter notebooks.

# Why Deep Learning - Use Cases

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

# What is DL?

- Subfield of ML, train artificial NNs on huge amounts of data
- NNs are types of ML models, composed of nodes, each node == 1 unit of computation
- Nodes connected by weights - representing strength between nodes

- During training process, NN is fed a huge amount of data
- Weights adjusted to minimize error between predicted output and true output, done through an optimization algo (e.g. stochastic gradient descent: iteratively adjusts weights to minimize error)

- Overfitting: when model performs well on training data, but poorly on new, unseen data.
  -- Occurs when model has too many parameters, too complex, which causes it to fit the training data too closely.
  -- To prevent overfitting, we use regularization techniques, e.g. adding a penalty to loss function, or dropout - randomly removes nodes from model during training.

- How do we find the sweet spot b/w over/underfitting?
  > This is the "bias-variance tradeoff"

---

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

## What do we need to train a model?

1. Data
2. Labels
3. Loss function to measure performance of the model
4. Optimizer to update parameters

## How?

1. Download a dataset of dog, cat photos
2. Train a model using dataset (bunch of images, emails, sounds - any data)

# Q and A

### What impacts training time?

- Network speed
- Usually a few minutes to train
- Keep reading next section while model trains/work on other notebooks

### What does Jupyter always print?

- Prints/shows result of last line

### How do we know if a model is good?

- Look at Error Rate (prop of images that were incorrectly ID'd)

### What is a DataBlock?

- FastAI boils down common traits of data into 5 things:

_Format_
`dls = DataBlock(`blocks`, `get_items`, `splitter`, `get_y`, `item_tfms`).dataloaders(path)`

1. `blocks` Kind of i/o (e.g. `ImageBlock` / `CategoryBlock`)
2. `get_items` Function (that returns a list)
3. `splitter` A validation center (randomly set aside 20% of data = `valid_pct=0.2`)
4. `get_y` Function that returns parent folder of a path (need to know if a label is correct - if bird or forest photo)
5. `item_tfms` (Item transforms) How do you want to transform every photo / data piece

`dls.show_batch(max_n=6)`

- "Show batch" means show a batch of data as example of what you'll pass into the model. Shows you input + label (which comes from calling the `get_y` function)

Examples of `splitters` and `get_y`:

- docs.fast.ai -> tutorials -> DataBlock tutorials

### How do we find the sweet spot between

# Best Practices

- Display your data once you init them, so you can check if they look reasonable (e.g. displaying thumbnail of a bird)
