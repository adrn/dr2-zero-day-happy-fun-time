Do we want AVG(EXP(a_g_val))?

SELECT
  gaia_healpix_index(11, source_id) AS healpixy,
  count(*) AS num,
  SUM(a_g_val*a_g_val) AS a_g_sum_sq,
  AVG(a_g_val) AS avg_a_g
FROM gaiadr2.gaia_source
WHERE (parallax < 1) AND (parallax IS NOT NULL) AND (a_g_val IS NOT NULL)
GROUP BY healpixy
