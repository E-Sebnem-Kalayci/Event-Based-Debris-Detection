# Event-Based-Debris-Detection

In comparison to frame based cameras that capture full images at a fixed rate, event cameras are less data heavy and more efficient by having each pixel operate independently and only storing the moments when there is a significant change in the polarity (brightness) of the pixels (when there is movement in the scene).

Event cameras doesn't store frames, they store 'events' which is formatted as (x, y, t, p) == x and y coordinates of pixels, timestamps, polarity change (this is different for each camera type. Our study is based on the EVK-4 which stores polarity as 1 (increase in brightness) and 0 (decrease in brightness))

# Event to Frame Construction
If data is not stored as images but only as text files how are we going to turn these events into actual images to see the object? This algortihm could be coded with the Python or C++ API provided by Prophesee https://docs.prophesee.ai/stable/guides/frames_generators.html as a *next step*. However without access to an event camera, we are using the Florence RGB Event Dataset that has events already converted into images to test our detection and tracking codes.

Our algorithm's purpose is to first detect any debris approaching the satellite, track the detected debris with a green box, determine how fast the object is approaching the satellite, to later trigger reaction mechanisms.

# Denoise
...see the code...

# Detect
...see the code...

# Track
...see the code...

# Velocity & Warning (*next step*)
Since our algorithm is for warning against potential collisions between the camera-mounted satellite and the debris approaching, we only care about the velocity of object in the z-dimension. This could be calculated by how much the object is becoming to seem bigger or smaller over time (how fast the dimensions of the green box around detected object is changing)

if V_z direction is positive = the object is becoming bigger looking, approaching the satellite (needs to send a warning message)

if negative = vice versa


# Citations:
@inproceedings{magrini2025fred,
  title={FRED: The Florence RGB-Event Drone Dataset},
  author={Magrini, Gabriele and Marini, Niccol{`o} and Becattini, Federico and Berlincioni, Lorenzo and Biondi, Niccol{`o} and Pala, Pietro and Del Bimbo, Alberto},
  booktitle={Proceedings of the 33rd ACM International conference on multimedia},
  year={2025}}

@article{magrini2025fred,
  title={FRED: The Florence RGB-Event Drone Dataset},
  author={Magrini, Gabriele and Marini, Niccol{\`o} and Becattini, Federico and Berlincioni, Lorenzo and Biondi, Niccol{\`o} and Pala, Pietro and Del Bimbo, Alberto},
  journal={arXiv preprint arXiv:2506.05163},
  year={2025}}



*Literature Review:*
https://www.northropgrumman.com/who-we-are/the-facts/digital-transformation/neuromorphic-cameras-provide-a-vision-of-the-future

https://engineering.jhu.edu/ece/news/2-million-darpa-contract-to-advance-bio-inspired-event-based-cameras-in-3d-cmos-technology/

https://aerospace.org/article/space-debris-101#:~:text=Mathematical%20modeling%20has%20repeatedly%20shown,every%20five%20to%20ten%20years. 

https://pmc.ncbi.nlm.nih.gov/articles/PMC12610280/

https://www.spacefoundation.org/space_brief/space-situational-awareness/

https://www.nasa.gov/smallsat-institute/sst-soa/identification-and-tracking-systems/#12.2

https://www.mdpi.com/1424-8220/25/9/2900

https://arxiv.org/abs/2506.16436

https://www.nature.com/articles/s41586-024-07409-w#Sec6

https://arxiv.org/abs/2506.16436

https://arxiv.org/pdf/2203.13093 

https://www.scientificamerican.com/article/the-space-junk-crisis-needs-a-recycling-revolution/

https://www.prophesee.ai/2025/12/02/event-sensors-bring-just-the-right-data-to-device-makers/#:~:text=By%202010%2C%20researchers%20at%20the,exploring%20and%20implementing%20event%20sensors

https://sites.google.com/view/guillermogallego/research/event-based-vision 

https://www.ids-imaging.us/technical-articles-details/items/beyond-frame-rate.html

https://www.advancedsciencenews.com/bio-inspired-robotic-eyes-that-better-estimate-motion/

https://arxiv.org/html/2302.08890v3
