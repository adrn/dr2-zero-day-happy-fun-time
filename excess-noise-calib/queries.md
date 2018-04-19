- APOGEE cross-match query
- RV error^2 vs. K^2 - should be a linear relationship
- (KP)^2 vs. excess astrometric variance / parallax^2 - lines of sini
- Giants (TwoFace) and main sequence (El-Badry)

radial_velocity
radial_velocity_error

rv_nb_transits (number of transits used to get median RV)
phot_variable_flag (0=n/a, 1=constant, 2=variable)

phot_rp_mean_mag (Rp magnitude)
phot_rp_mean_flux (Rp flux)
phot_rp_mean_flux_err

phot_bp_mean_mag (Bp magnitude)
phot_bp_mean_flux (Bp flux)
phot_bp_mean_flux_err


SELECT * FROM gaia_source
WHERE (rv_nb_transits >= 3) and ??