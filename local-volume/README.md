# Local volume

Queries to select out local volumes for playing around.

* Sphere, 100 pc

    SELECT *
    FROM gaiadr2.gaia_source
    WHERE parallax > 10

* Sphere, 200 pc

    SELECT *
    FROM gaiadr2.gaia_source
    WHERE parallax > 5

* Cylinder, 100 pc R radius, 750 pc in z

    SELECT *
    FROM gaiadr2.gaia_source             
    WHERE ((1000/parallax)*COS(RADIANS(b))) < 100
    AND ABS((1000/parallax)*SIN(RADIANS(b))) < 750

* Cylinder, 1.5 kpc R radius, 750 pc in z

    SELECT *
    FROM gaiadr2.gaia_source             
    WHERE ((1000/parallax)*COS(RADIANS(b))) < 1500
    AND ABS((1000/parallax)*SIN(RADIANS(b))) < 750
