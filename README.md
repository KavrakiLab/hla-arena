# HLA-Arena
A customizable environment for the structural modeling and analysis of peptide-HLA complexes

## HLA-Arena installation
1. If you don’t already have it, install Docker.

    Docker for Mac or Windows: https://www.docker.com/products/docker-desktop

    Docker for Linux: https://docs.docker.com/install

2. In a command prompt, pull the HLA-Arena image from Docker Hub by typing:

        docker pull kavrakilab/hla-arena

3. Create a folder in which you want to run the workflows (optional).

4. Copy HLA-Arena notebooks and associated data to your local machine by typing:

        docker run --rm -v $(pwd):/temp --entrypoint cp kavrakilab/hla-arena /hla_arena_data/data.tar.gz \
        /temp/; tar -xzvf data.tar.gz

5. Run HLA-Arena in this folder by typing:

        docker run --rm -v $(pwd):/data -p 8888:8888 --entrypoint="" kavrakilab/hla-arena jupyter \
        notebook --port=8888 --no-browser --ip=0.0.0.0 --allow-root

6. This should generate a URL with the following format:

        http://127.0.0.1:8888/?token=<token_value>

7. Copy and paste this URL into a browser, and open any available Jupyter notebook (i.e., one of
the files with extension .ipynb). Note that all the data created in the container will be saved inside
sub-directories of the current folder.

8. Check out the [DOCUMENTATION](https://kavrakilab.github.io/hla-arena/), also provided alongside the Jupyter notebooks, for
additional information on the workflows and available functions. 

    Enjoy HLA-Arena!
