#include <stdio.h>

int main(void) {
    /* ===== Variables (tu peux modifier) ===== */
    int  speed   = 123;          /* vitesse */
    char su[]    = "km/h";       /* unité vitesse: "km/h" "kts" "mph" */

    int  alt     = 1450;         /* altitude */
    char au[]    = "m";          /* unité altitude: "m" ou "ft" */

    int  vsi     = +500;         /* variomètre (m/min ou ft/min selon ton choix) */

    int  pitch   = +5;           /* assiette (°) */
    int  bank    = +15;          /* roulis (°)  */
    int  hdg     = 215;          /* cap (° 0..359) */

    /* ===== Tableau de bord ASCII (≈75x25) — seulement des printf ===== */
    printf("+-----------------------------------------------------------------------+\n");
    printf("|%03d                                                                    %4d|\n", speed+40, alt+400);
    printf("|                                                                       |\n");
    printf("|                                                                       |\n");
    printf("|%03d                                                                    %4d|\n", speed+30, alt+300);
    printf("|                                                                       |\n");
    printf("|                                                                       |\n");
    printf("|%03d                    PITCH:%+3d%c     BANK:%+3d%c                        %4d|\n",
           speed+20, pitch, 248 /*° ASCII alt*/, bank, 248, alt+200);
    printf("|                          --- HORIZON ---                               |\n");
    printf("|                          --   -+-   --                                 |\n");
    printf("|%03d                                                                    %4d|\n", speed+10, alt+100);
    printf("|                                  |                                    |\n");
    printf("|%03d                          -----------                               %4d|\n", speed+0, alt+0);
    printf("|                                  |                                    |\n");
    printf("|%03d                                                                    %4d|\n", speed-10, alt-100);
    printf("|                                                                       |\n");
    printf("|                                                                       |\n");
    printf("|%03d                                                                    %4d|\n", speed-20, alt-200);
    printf("|                                                                       |\n");
    printf("|                                                                       |\n");
    printf("|%03d                                                                    %4d|\n", speed-30, alt-300);
    printf("|                                                                       |\n");
    printf("|                                                                       |\n");
    printf("|%03d                                                       VSI:%+5d   %4d|\n", speed-40, vsi, alt-400);
    printf("|[%s]                                                              [%s]|\n", su, au);
    printf("+-----------------------------------------------------------------------+\n");
    printf("|         W           |           HDG:%03d°            |           E         |\n", (hdg%360+360)%360);
    printf("|      |.....|.....|..|.....|.....|.....|.....|..|.....|..|.....|.....|      |\n");
    printf("|           240       |      270      300      330      |       060           |\n");
    printf("|            S        |            N           ^         |         NE          |\n");
    printf("+-----------------------------------------------------------------------+\n");
return 0;
}
