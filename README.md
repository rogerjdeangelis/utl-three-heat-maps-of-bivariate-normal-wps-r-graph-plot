# utl-three-heat-maps-of-bivariate-normal-wps-r-graph-plot
Three heat maps of bivariate normal wps r graph plot
    %let pgm=utl-three-heat-maps-of-bivariate-normal-wps-r-graph-plot;

    Three heat maps of bivariate normal wps r graph plot;

    Remarkable set of three graphs?

    http://tinyurl.com/46ywn7pu  
    https://github.com/rogerjdeangelis/utl-three-heat-maps-of-bivariate-normal-wps-r-graph-plot/blob/main/topo.pdf

    github
    http://tinyurl.com/46ywn7pu
    https://github.com/rogerjdeangelis/utl-three-heat-maps-of-bivariate-normal-wps-r-graph-plot

    Related repos
    https://github.com/rogerjdeangelis/utl-heat-map-of-correlation-matrix
    https://github.com/rogerjdeangelis/utl_heatmap

    see
    http://rgraphgallery.blogspot.com/2013/04/rg-add-countour-or-heat-map-plot-to-xy.html

    /*               _     _
     _ __  _ __ ___ | |__ | | ___ _ __ ___
    | `_ \| `__/ _ \| `_ \| |/ _ \ `_ ` _ \
    | |_) | | | (_) | |_) | |  __/ | | | | |
    | .__/|_|  \___/|_.__/|_|\___|_| |_| |_|
    |_|
    */

    /**************************************************************************************************************************/
    /*                                                                                                                        */
    /*             INPUT                                                        OUTPUT                                        */
    /*                                                                                                                        */
    /*    Obs        X              Y                    -10            0            10            20            30           */
    /*                                                  --+-------------+-------------+-------------+-------------+-          */
    /*      1     13.1060     28.7360                 Y |                                                          |          */
    /*      2      9.3845     18.9521                60 +  Bivariate normal density                                +   60     */
    /*      3     11.5022     15.3326                   |                                                          |          */
    /*      4     11.5526     12.1421                   |                                        ****              |          */
    /*      5      8.1719     11.4159                   |                                      ###****#             |         */
    /*      6     15.0770     12.1659                   |                                    ###########           |          */
    /*      7     12.4549     13.0093                   |                              ##-################         |          */
    /*      8     13.1318     17.0033                   |                             -#--#####*####*****          |          */
    /*      9      5.7067     15.0899                40 +                             ------###########*#          +   40     */
    /*     10      5.6530      5.8861                   |                          --------------#########         |          */
    /*     11      5.5965     -0.2680                   |                         ------------------####           |          */
    /*     12     13.6268      2.4044                   |                      -----------------------###          |          */
    /*     13     -1.8405     -2.4351                   |                     XXX-------------------------         |          */
    /*     14      3.7012     24.4246                   |                  XXXXXXXXX-X-------------------          |          */
    /*     15      2.6330     15.7224                   |                   XXXXXXXXXXXXX-X-------------           |          */
    /*     16      9.7909     15.3393                20 +               XXXXXXXXXXXXXXXXXXXX-XX----------           +   20    */
    /*     17      8.1690     11.1378                   |                XXXXXXXXXXXXXXXXXXXXXXX-------            |          */
    /*     18      8.1961      9.2540                   |           +++++XXXXXXXXXXXXXXXXXXXXXXXXXXXX              |          */
    /*     19     12.8815     14.6141                   |          ++++++++++++XXXXXXXXXXXXXXXXXXXXXX              |          */
    /*    ...                                           |             +++++++++++++XXXXXXXXXXXXXX XX               |          */
    /*                                                  |           + +++++++++++++++XX+XXXXXXX XXX                |          */
    /*                                                  |            +++++++++++++++++++++XXXXXXX                  |          */
    /*                                                0 +           + +++++++++++++++++++++++X                     +    0     */
    /*                                                  |            ..+.++++++++++++++++++                        |          */
    /*                                                  |           ........+.+++++++++++++++                      |          */
    /*                                                  |             ........++.++++++++++                        |          */
    /*                                                  |          ................+..+                            |          */
    /*                                                  |             ...............                              |          */
    /*                                                  |                   ....                                   |          */
    /*                                              -20 +                    .                                     +  -20     */
    /*                                                  --+-------------+-------------+-------------+-------------+-          */
    /*                                                   -10            0            10            20            30           */
    /*                                                                                                                        */
    /*                                                                                X                                       */
    /*                                                                                                                        */
    /*                                                  Symbol                  Z     Symbol                  Z               */
    /*                                                                                                                        */
    /*                                                  .....   -220.47 -  -31.78     -----    345.61 -  534.30               */
    /*                                                  +++++    -31.78 -  156.91     #####    534.30 -  722.99               */
    /*                                                  XXXXX    156.91 -  345.61                                             */
    /*                                                                                                                        */
    /*                                                                                                                        */
    /**************************************************************************************************************************/

    /*                   _
    (_)_ __  _ __  _   _| |_
    | | `_ \| `_ \| | | | __|
    | | | | | |_) | |_| | |_
    |_|_| |_| .__/ \__,_|\__|
            |_|
    */

    options validvarname=upcase;
    libname sd1 "d:/sd1";
    data sd1.have(drop=rec z);;
      call streaminit(5731);
      do rec=1 to 10000;
         x=rand('normal',10,4);
         y = 1.5*x + rand('normal',0,8);
         z=  10*(x+y);;
         output;
      end;
    run;quit;

    /* keep z if you want tn ascii plot
    options ls=64 ps=44;
    proc plot data=sd1.have;
    plot y*x=z / contour=5 vaxis=-20 to 60 by 20 box;
    run;quit;
    */

    /**************************************************************************************************************************/
    /*                                                                                                                        */
    /* SD1.HAVE total obs=10,000                                                                                              */
    /*                                                                                                                        */
    /*   Obs        X              Y                                                                                          */
    /*                                                                                                                        */
    /*     1     13.1060     28.7360                                                                                          */
    /*     2      9.3845     18.9521                                                                                          */
    /*     3     11.5022     15.3326                                                                                          */
    /*     4     11.5526     12.1421                                                                                          */
    /*     5      8.1719     11.4159                                                                                          */
    /*     6     15.0770     12.1659                                                                                          */
    /*     7     12.4549     13.0093                                                                                          */
    /*     8     13.1318     17.0033                                                                                          */
    /*     9      5.7067     15.0899                                                                                          */
    /*    10      5.6530      5.8861                                                                                          */
    /*    11      5.5965     -0.2680                                                                                          */
    /*   .....                                                                                                                */
    /*                                                                                                                        */
    /**************************************************************************************************************************/

    /*
     _ __  _ __ ___   ___ ___  ___ ___
    | `_ \| `__/ _ \ / __/ _ \/ __/ __|
    | |_) | | | (_) | (_|  __/\__ \__ \
    | .__/|_|  \___/ \___\___||___/___/
    |_|
    */

    %utlflil(d:/pdf/topo.pdf);

    %utl_submit_wps64x('
    libname sd1 "d:/sd1";
    proc r;
    export data=sd1.have r=have;
    submit;
    library(haven);
    library(MASS);
    head(have);
    library(RColorBrewer);
    library(KernSmooth);
    pdf("d:/pdf/topo.pdf",10,8);
    attach(have);
    g=11;
    my.cols <- rev(brewer.pal(g, "RdYlBu"));
    z <- kde2d(X, Y, n=50);
    plot(X, Y, xlab="X", ylab="Y", pch=19, cex=.3, col = "gray60");
    contour(z, drawlabels=FALSE, nlevels=g, col=my.cols, add=TRUE, lwd = 2);
    abline(h=mean(Y), v=mean(X), lwd=2, col = "black");
    legend("topleft", paste("r=", round(cor(X, Y),2)), bty="n");
    prob <- c(.99, .95, .90, .8, .5, .1, 0.05);
    dx <- diff(z$x[1:2]);
    dy <- diff(z$y[1:2]);
    sz <- sort(z$z);
    c1 <- cumsum(sz) * dx * dy;
    levels <- sapply(prob, function(x) {
        approx(c1, sz, xout = 1 - x)$y });
    plot(X,Y, col = "gray80", pch = 19, cex = 0.3);
    contour(z, levels= round (levels,7), add=T, col = "red");
    smoothScatter(X, Y, nrpoints=3000, colramp=colorRampPalette(my.cols), pch=19, cex=.3, col = "green1");
    endsubmit;
    ');

    /*           _               _
      ___  _   _| |_ _ __  _   _| |_
     / _ \| | | | __| `_ \| | | | __|
    | (_) | |_| | |_| |_) | |_| | |_
     \___/ \__,_|\__| .__/ \__,_|\__|
                    |_|
    */


    /**************************************************************************************************************************/
    /*                                                                                                                        */
    /*                                 OUTPUT                                                                                 */
    /*                                                                                                                        */
    /*          -10            0            10            20            30                                                    */
    /*         --+-------------+-------------+-------------+-------------+-                                                   */
    /*       Y |                                                          |                                                   */
    /*      60 +  Bivariate normal density                                +   60                                              */
    /*         |                                                          |                                                   */
    /*         |                                        ****              |                                                   */
    /*         |                                      ###****#            |                                                   */
    /*         |                                    ###########           |                                                   */
    /*         |                              ##-################         |                                                   */
    /*         |                             -#--#####*####*****          |                                                   */
    /*      40 +                             ------###########*#          +   40                                              */
    /*         |                          --------------#########         |                                                   */
    /*         |                         ------------------####           |                                                   */
    /*         |                      -----------------------###          |                                                   */
    /*         |                     XXX-------------------------         |                                                   */
    /*         |                  XXXXXXXXX-X-------------------          |                                                   */
    /*         |                   XXXXXXXXXXXXX-X-------------           |                                                   */
    /*      20 +               XXXXXXXXXXXXXXXXXXXX-XX----------           +   20                                             */
    /*         |                XXXXXXXXXXXXXXXXXXXXXXX-------            |                                                   */
    /*         |           +++++XXXXXXXXXXXXXXXXXXXXXXXXXXXX              |                                                   */
    /*         |          ++++++++++++XXXXXXXXXXXXXXXXXXXXXX              |                                                   */
    /*         |             +++++++++++++XXXXXXXXXXXXXX XX               |                                                   */
    /*         |           + +++++++++++++++XX+XXXXXXX XXX                |                                                   */
    /*         |            +++++++++++++++++++++XXXXXXX                  |                                                   */
    /*       0 +           + +++++++++++++++++++++++X                     +    0                                              */
    /*         |            ..+.++++++++++++++++++                        |                                                   */
    /*         |           ........+.+++++++++++++++                      |                                                   */
    /*         |             ........++.++++++++++                        |                                                   */
    /*         |          ................+..+                            |                                                   */
    /*         |             ...............                              |                                                   */
    /*         |                   ....                                   |                                                   */
    /*     -20 +                    .                                     +  -20                                              */
    /*         --+-------------+-------------+-------------+-------------+-                                                   */
    /*          -10            0            10            20            30                                                    */
    /*                                                                                                                        */
    /*                                       X                                                                                */
    /*                                                                                                                        */
    /*         Symbol                  Z     Symbol                  Z                                                        */
    /*                                                                                                                        */
    /*         .....   -220.47 -  -31.78     -----    345.61 -  534.30                                                        */
    /*         +++++    -31.78 -  156.91     #####    534.30 -  722.99                                                        */
    /*         XXXXX    156.91 -  345.61                                                                                      */
    /*                                                                                                                        */
    /*                                                                                                                        */
    /**************************************************************************************************************************/


    /*              _
      ___ _ __   __| |
     / _ \ `_ \ / _` |
    |  __/ | | | (_| |
     \___|_| |_|\__,_|

    */
