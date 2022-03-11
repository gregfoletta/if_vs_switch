
# GCC Version

```
gcc --version
gcc (Ubuntu 9.4.0-1ubuntu1~20.04) 9.4.0
```

# Compilation

```
gcc main_if.c -o if
gcc main_switch.c -o switch
```

```
sudo perf stat ./if $(perl -E 'print "a " x 2000')

              0.77 msec task-clock                #    0.493 CPUs utilized
                 0      context-switches          #    0.000 /sec
                 0      cpu-migrations            #    0.000 /sec
                60      page-faults               #   77.614 K/sec
         1,146,698      cycles                    #    1.483 GHz
         1,048,753      instructions              #    0.91  insn per cycle
           205,947      branches                  #  266.406 M/sec
             8,480      branch-misses             #    4.12% of all branches
         5,733,490      slots                     #    7.417 G/sec
         1,191,666      topdown-retiring          #     20.8% retiring
           697,012      topdown-bad-spec          #     12.2% bad speculation
         1,888,679      topdown-fe-bound          #     32.9% frontend bound
         1,956,131      topdown-be-bound          #     34.1% backend bound

       0.001568765 seconds time elapsed

       0.001672000 seconds user
       0.000000000 seconds sys
```


```
sudo perf stat ./switch $(perl -E 'print "a " x 2000')

              0.73 msec task-clock                #    0.484 CPUs utilized
                 0      context-switches          #    0.000 /sec
                 0      cpu-migrations            #    0.000 /sec
                58      page-faults               #   79.472 K/sec
         1,085,178      cycles                    #    1.487 GHz
         1,029,153      instructions              #    0.95  insn per cycle
           201,191      branches                  #  275.673 M/sec
             6,402      branch-misses             #    3.18% of all branches
         5,425,890      slots                     #    7.435 G/sec
         1,170,290      topdown-retiring          #     21.6% retiring
           617,062      topdown-bad-spec          #     11.4% bad speculation
         1,574,572      topdown-fe-bound          #     29.0% frontend bound
         2,063,966      topdown-be-bound          #     38.0% backend bound

       0.001508958 seconds time elapsed

       0.001560000 seconds user
       0.000000000 seconds sys
```
