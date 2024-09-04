# gordic_knot

The idea is to create a pipeline that can design a novel protein containing a knot.
We run in a loop combination of designing a protein with diffusion followed by guiding the designed structure towards being knotted using a knot classifier model.

Scripts: [Flipping pipeline](Flipping_pipeline.ipynb)

### Part 1: Protein Design with diffusion

We are now using [foldingdiff](https://github.com/microsoft/foldingdiff) model to design the protein backbone.

### Part 2: Knot Classifier

Datasets for training the knot classifier: https://huggingface.co/datasets/EvaKlimentova/foldingdiff_knots

Models are trained on the above datasets. They use as inputs the same format as is used in foldingdiff (6-tuple of angles).
I tried two model architectures: a simple feedforward neural network and a CNN.

Scripts: [Feed forward neural network](Flip_structure.ipynb), [CNN](Flip_structure_CNN.ipynb)

Models: [models folder](models)

### Other things

To better understand what is happening with the structure, we have a script that visualizes the structure in 3D and makes a video of the structure change. See [the video folder](pdb_video).