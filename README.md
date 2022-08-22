# RPL-Rank-Attacks
In this repository, we have used the Cooja simulator which is part of the [Contiki OS](https://github.com/contiki-os/contiki) to implement a number of rank attacks on RPL. RPL is the major protocol which is being used in IoT devices.

## What to change
In order to implement the attacks in Cooja, some changes should be applied to the source codes. These changes are stated below for each attack:
 - Decreased Rank Attack:  
   - RPL_CONF_MIN_HOPRANKINC is set to 0 in udp_sender.c of attacker node
   - RPL_MAX_RANKINC is set to 0 in rpl-private.h
   - rpl_recalculate_ranks() is removed from rpl-timers.c
 - Increased Rank Attack:
   - best_parent() return statement is changed to 'return p1_metric > p2_metric ? p1 : p2' in rpl-mrhof.c
   - rpl_recalculate_ranks() is removed from rpl-timers.c
 - Worst Parent Selection Attack:
   - calculate_rank() return statement is set to INFINITE_RANK in rpl-mrhof.c
   - rpl_recalculate_ranks() is removed from rpl-timers.c
