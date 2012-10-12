# Geohash-based spatial indexing

## random notes

- good at point data, more complex for line/poly
- relatively easy to implement bounding box
- expensive to implement k-NN

based on Z-order curve:
(trace with finger)

    1   2   5   6

    3   4   7   8

    9  10  13  14

    11 12  15  16

can be improved in certain cases by using Hilbert curves [instead](blog.notdot.net/2009/11/Damn-Cool-Algorithms-Spatial-indexing-with-Quadtrees-and-Hilbert-Curves) (smarter contiguous range queries)

recursive leaf splitting http://www.cs.umd.edu/~hjs/pubs/NelsSIGG86.pdf

alternative approach: hypercube ray tracing!???

### indexing polygons

if you just store each point in the polygon then only queries that intersect with an edge of the polygon will work. queries that are entirely inside the polygon won't be able to detect that they are inside a polygon

