
Ran a service in Instance - Ping Google.com

> Now in another Instance I ran Process Commands top , htop & pgrep

  >> top command gave me basic text only interface of processes for monitoring.
  >> htop command gave me interactive interface for monotoring, it is quick and it also offers vertical/horizontal scrolling,         easier process kiiling.
  >> pgrep command filter the running process based on the given criteris(eg. pattern, user Id, name) and it lists all process         ids of those matches.
        { pgrep ping (find all running  process starts with ping)}
        { pgrep -l ping(-l(list name) option displays both PID and process name }
