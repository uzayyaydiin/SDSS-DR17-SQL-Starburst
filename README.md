# SDSS-DR17-SQL-Starburst

With this query you can access Starburst galaxy data from the SDSS DR17 catalog.


SELECT 
p.objid,p.ra,p.dec,p.u,p.g,p.r,p.i,p.z,
p.run, p.rerun, p.camcol, p.field,
p.extinction_u, p.extinction_g, p.extinction_r, p.extinction_i, p.extinction_z,
p.dered_u, p.dered_g, p.dered_r, p.dered_i, p.dered_z,
s.specobjid, s.class, s.z as redshift,
s.plate, s.mjd, s.fiberid
FROM PhotoObj AS p
JOIN SpecObj AS s ON s.bestobjid = p.objid
WHERE s.subclass="Starburst"
