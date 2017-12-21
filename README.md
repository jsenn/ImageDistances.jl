# ImageDistances.jl

[![Build Status](https://travis-ci.org/JuliaImages/ImageDistances.jl.svg?branch=master)](https://travis-ci.org/JuliaImages/ImageDistances.jl)
[![Coverage Status](https://coveralls.io/repos/JuliaImages/ImageDistances.jl/badge.svg?branch=master&service=github)](https://coveralls.io/github/JuliaImages/ImageDistances.jl?branch=master)
[![codecov.io](http://codecov.io/github/JuliaImages/ImageDistances.jl/coverage.svg?branch=master)](http://codecov.io/github/JuliaImages/ImageDistances.jl?branch=master)

Distances between images following the [Distances.jl](https://github.com/JuliaStats/Distances.jl) API.

## Installation

Get the latest stable release with Julia's package manager:

```julia
Pkg.add("ImageDistances")
```

## Usage

Given two N-dimensional images `imgA` and `imgB`, and any of the distances `d` defined in this package,
we can evaluate the following expressions:

```julia
using Distances
using ImageDistances

d = ModifiedHausdorff()

# distance between the two images
evaluate(d, imgA, imgB)

# two lists of images
imgsA = [imgA, imgB, ...]
imgsB = [imgB, imgA, ...]

# distance between the "columns"
colwise(d, imgsA, imgsB)

# distance between every combination of 2
pairwise(d, imgsA, imgsB)
```

Like in Distances.jl, huge performance gains are obtained by calling the `colwise` and `pairwise`
functions instead of naively looping over a collection of images and calling `evaluate`.

## Distances

| Distance | References |
|----------|------------|
| `Hausdorff` and `ModifiedHausdorff` | Dubuisson, M-P et al. 1994. A Modified Hausdorff Distance for Object-Matching |

## Contributing

Contributions are very welcome, as are feature requests and suggestions.

Please [open an issue](https://github.com/juliohm/ImageDistances.jl/issues) if you encounter
any problems.