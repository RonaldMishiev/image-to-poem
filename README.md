Image to Poem: Translating Visual Aesthetics into Poetic Expression

For this project, we became interested in the possibility of being able to generate text from an image. 
Not just any text though, we were determined to be able to produce a poem from any picture. The idea was to 
translate the context of an image into a form of expressive text — a poem. For this, we implemented various measures 
to ensure a successful endeavor, ranging from the use of an LTSM model to regularization/overfitting features 
like ES and RMSprop, all of which will be explained in the proceeding sections.

## The Data

We utilized the Gutenberg Poetry Corpus, which comprises millions of lines of poetry, each associated with its poem's ID. 
We preprocessed the text data to remove non-ASCII characters, making it more LSTM-friendly by mapping unique characters to indices. 
For image processing, we chose DenseNet121 pre-trained on ImageNet for its efficiency and performance on limited computational resources.

## How It Works

Our model architecture integrates image recognition with poem generation. 
The image model (DenseNet121) predicts the contents of an image, passing significant observations to the LSTM-based poem model as a seed. 
The LSTM model, optimized with RMSprop and regulated through Early Stopping, generates the poem text, 
leveraging the patterns learned from the Gutenberg Poetry Corpus.

### LSTM Model

LSTM, or Long Short-Term Memory model, is a type of RNN particularly 
adept at learning long-term dependencies, making it ideal for sequence data like poetry.

### RMSprop

An optimization technique that improves stability for smaller batch sizes and ensures similar gradient updates across mini-batches.

### Early Stopping

A regularization technique to prevent overfitting by halting training when the validation set accuracy diverges from the training set.

## The Training & Testing Process

Our journey began with a simple LSTM architecture, which we iteratively refined by increasing complexity and tuning hyperparameters.

## Final Showcase

The trained model can now produce poems that, while not always perfectly coherent, capture the creative essence of the corpus it was trained on. 

## References

- [Generating Poems for Any Given Image Using Multi-Modal Machine Learning](https://medium.com/towards-generative-ai/generating-poems-for-any-given-image-using-multi-modal-machine-learning-2be35b72f50a)
- [Understanding RMSprop - Faster Neural Network Learning](https://towardsdatascience.com/understanding-rmsprop-faster-neural-network-learning-62e116fcf29a)
- [Gutenberg Poetry Corpus Dataset](https://huggingface.co/datasets/biglam/gutenberg-poetry-corpus/viewer/cakiki--gutenberg-poetry-corpus/train?p=30851)

## Acknowledgments

Images sourced from the public domain on [The New York Public Library Digital Collections](https://digitalcollections.nypl.org/).
