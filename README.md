Kyle Newbigging 1093959

1. Features I implemented and why

    Closest "capsule" or power pellet:
        Did this because pacman tends to avoid this otherwise

    Closest Scared Ghost:
        Allows for pacman to determine if going for that ghost is "worth" it
        (Wish I had more time to optimize with the scared timer and distance away from pacman)

    Closest Food:
        modified with only considering ghosts that are not scared

    Average Scores: Got averages with the following:
            python3 pacman.py -p ApproximateQAgent -a extractor=myExtractor -x 50 -n 60 -l myLayout
        mediumGrid: 528.0
        mediumClassic: 1457.5


2. My Layout has 4 ghosts for a small area with more power pellets than normal layouts.
This results is way higher scores due to the SimpleExtractor not considering the ghosts being scared

Average Score on mylayout:
python3 pacman.py -p ApproximateQAgent -a extractor=SimpleExtractor -x 50 -n 60 -l myLayout

myExtractor: 1835.0
SimpleExtractor: 1743.0
