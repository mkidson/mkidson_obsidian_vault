options:

- n std devs away from the gamma peak. linear interp between them. should work down to about 0.4 MeVee
- Same as above but when that point is within m std devs of the neutron edge, take a midpoint or use the neutron one etc
- midpoint between n std devs away from both peaks. When there’s overlap either do the same or

I think it’ll need some way of realising that it’s come to the end of one of the loci, so fitting no longer makes much sense. After this it should probably just stick with the last S value it chose and use that