---
title: "Keeping long-running compute jobs alive in jupyter"
collection: smarties
---

To run jupyter lab on a remote computer, and keep it alive when my local computer sleeps:

    ssh -L 8888:localhost:8888 ubuntu@<ip of remote machine>
    tmux new -n <name of session>
	cd <your project directory> # optional
	pipenv shell
	jupyter lab --no-browser --port=8888
    ctrl+b d

    -> local computer can go to sleep now! 😴

To get back to the computation:   

    ssh -L 8888:localhost:8888 ubuntu@<ip of remote machine>
    tmux attach
