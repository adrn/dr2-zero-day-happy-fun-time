# Quick query to grab hypervelocity star candidates

* What is our velocity cutoff? I arbitrarily chose 400 and 300
* Local volume with parallax measurements:
```
SELECT *
FROM gaiadr2.gaia_source
WHERE (phot_g_mean_mag < 18) AND
      (parallax > 1) AND (parallax/parallax_error > 6) AND
      ((radial_velocity IS NOT NULL AND
        SQRT(POWER(pmra/parallax * 4.7404705, 2) +
             POWER(pmdec/parallax * 4.7404705, 2) +
             POWER(radial_velocity, 2)) > 400) OR
       (radial_velocity IS NULL AND
        SQRT(POWER(pmra/parallax * 4.7404705, 2) +
             POWER(pmdec/parallax * 4.7404705, 2)) > 300))
```
* Distant volume with no parallax but large proper motion. 20 mas/yr at 4 kpc = 400 km/s:
```
SELECT *
FROM gaiadr2.gaia_source
WHERE (phot_g_mean_mag < 18) AND
      ((parallax < 1) OR (parallax/parallax_error < 2)) AND
      (pmra/pmra_error > 6 AND pmdec/pmdec_error > 6 AND
       SQRT(POWER(pmra, 2) + POWER(pmdec, 2)) > 20)
```
