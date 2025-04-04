# CBT547
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. GitHub repos will be deleted and created during this period...

```
//***FILE 547 is from Volker Bandke, who has pioneered the easy     *   FILE 547
//*           setup of a Hercules Turnkey MVS system that runs      *   FILE 547
//*           free MVS 3.8J on your PC at home or at work.          *   FILE 547
//*                                                                 *   FILE 547
//*           This file of software has tools and JCL, and other    *   FILE 547
//*           stuff (such as the CMD Subsystem utilities) which     *   FILE 547
//*           run on MVS 3.8J, under Hercules, or a later MVS,      *   FILE 547
//*           to supplement Volker's Turnkey System.                *   FILE 547
//*                                                                 *   FILE 547
//*           -------------------------------------------------     *   FILE 547
//*                                                                 *   FILE 547
//*            MVS on your PC - Turnkey MVS System Utilities        *   FILE 547
//*                                                                 *   FILE 547
//*              Fortune Cookies, R2D2, and other goodies           *   FILE 547
//*                                                                 *   FILE 547
//*           -------------------------------------------------     *   FILE 547
//*                                                                 *   FILE 547
//*           In case you don't know yet, Hercules is a freeware    *   FILE 547
//*           hardware emulator which allows you to run any flavor  *   FILE 547
//*           of MVS, VM, VSE, LINUX/390, or anything else which    *   FILE 547
//*           runs on S/390 hardware, ON YOUR PC AT HOME....        *   FILE 547
//*                                                                 *   FILE 547
//*           Of course, if you can't run an operating system       *   FILE 547
//*           because of licensing restrictions, at least, you      *   FILE 547
//*           can run free old versions of MVS, VM, or DOS/VS.      *   FILE 547
//*                                                                 *   FILE 547
//*           That's what Volker's Turnkey MVS system makes it      *   FILE 547
//*           easy to do.  Volker already did a Full SYSGEN, and    *   FILE 547
//*           has set up a completely configured MVS system, which  *   FILE 547
//*           you can load up and run on your PC, just by answering *   FILE 547
//*           a few questions.  Setup time is a few minutes, and    *   FILE 547
//*           certainly less than half an hour.  Volker's Turnkey   *   FILE 547
//*           MVS 3.8J system cd-rom is available for ordering,     *   FILE 547
//*           at:                                                   *   FILE 547
//*                                                                 *   FILE 547
//*               http://www.cbttape.org                            *   FILE 547
//*                                                                 *   FILE 547
//*           Volker Bandke's email:                                *   FILE 547
//*               "Volker Bandke" <vbandke@bsp-gmbh.com>            *   FILE 547
//*                                                                 *   FILE 547
//*           - - - - - - - - - - - - - - - - - - - - - - - - -     *   FILE 547
//*                                                                 *   FILE 547
//*           This file contains five main members:                 *   FILE 547
//*                                                                 *   FILE 547
//*           ASM       -  IEBUPDTE (PDSLOAD) sequentialized PDS    *   FILE 547
//*                        This member contains some wonderful      *   FILE 547
//*                        programs, such as Volker's "Wisdom from  *   FILE 547
//*                        the Fortune Cookie Jar".  Also, it has a *   FILE 547
//*                        program to syntax check the APF Parmlib  *   FILE 547
//*                        members and a bunch of other useful      *   FILE 547
//*                        programs.                                *   FILE 547
//*                                                                 *   FILE 547
//*   Contents of ASM member:                                       *   FILE 547
//*                                                                 *   FILE 547
//*   I think 1973 translates to 2001, and 1974 to 2002.  (SG)      *   FILE 547
//*                                                                 *   FILE 547
//*   BRODSCAN           80.01  1974/03/23  1974/03/23 16:56   439  *   FILE 547
//*   BSPAPFCK           80.10  1974/01/08  1974/02/06 19:48   551  *   FILE 547
//*   BSPAPFLS           80.29  1974/03/23  1974/03/24 10:17   624  *   FILE 547
//*   BSPFCOOK           80.37  1974/01/23  2002/03/24 11:14   369  *   FILE 547
//*   BSPFCOO1                                                      *   FILE 547
//*   BSPFCOO2                                                      *   FILE 547
//*   BSPFCOO3                                                      *   FILE 547
//*   BSPFCOO4                                                      *   FILE 547
//*   BSPOSCMD           80.00  1974/03/23  1974/03/23 16:07   586  *   FILE 547
//*   BSPPA2SI           80.00  1974/03/23  1974/03/23 16:07   557  *   FILE 547
//*   BSPPILOT           80.29  1974/02/06  1974/03/24 10:05   530  *   FILE 547
//*   BSPRUNSC           80.69  1974/01/31  1974/03/24  6:25  1295  *   FILE 547
//*   BSPSETPF           80.93  1974/01/08  1974/03/24  6:28  1514  *   FILE 547
//*   BSPVTMWT           80.01  1974/02/07  1974/02/07 13:39    98  *   FILE 547
//*   DELAY              80.01  1974/03/23  1974/03/23 16:56   110  *   FILE 547
//*   IEECVXIT           80.22  1974/01/20  1974/02/07  9:44   648  *   FILE 547
//*   IEFACTRT                                                      *   FILE 547
//*   IKJEFTE2           80.00  1974/01/01  1974/01/01 16:24    18  *   FILE 547
//*   MOVELOAD           80.01  1974/03/23  1974/03/23 16:58   235  *   FILE 547
//*   REQUEUE            80.01  1974/03/23  1974/03/23 16:59   144  *   FILE 547
//*   TAPEHDR            80.04  1974/03/23  1974/03/23 18:08   460  *   FILE 547
//*                                                                 *   FILE 547
//*           CNTL      -  IEBUPDTE (PDSLOAD) sequentialized PDS    *   FILE 547
//*                        This PDS contains members needed to      *   FILE 547
//*                        set up the software packages and         *   FILE 547
//*                        programs that are in the other PDS'es    *   FILE 547
//*                        (which are members in this file).        *   FILE 547
//*                                                                 *   FILE 547
//*           MACLIB    -  IEBUPDTE (PDSLOAD) sequentialized PDS    *   FILE 547
//*                        Volker's Maclib - needed for ASM         *   FILE 547
//*                                                                 *   FILE 547
//*   Contents of MACLIB member:                                    *   FILE 547
//*                                                                 *   FILE 547
//*   $TITLE                                                        *   FILE 547
//*   @                                                             *   FILE 547
//*   BLANK                                                         *   FILE 547
//*   BOX                                                           *   FILE 547
//*   BSPAUTH            80.02  1974/01/23  1974/01/23 14:04    21  *   FILE 547
//*   BSPBEG                                                        *   FILE 547
//*   BSPEND                                                        *   FILE 547
//*   BSPENTER           80.00  1974/01/07  1974/01/07 22:57   138  *   FILE 547
//*   BSPGLBLS           80.00  1974/01/23  1974/01/23 14:02     7  *   FILE 547
//*   BSPPATCH                                                      *   FILE 547
//*   BSPRET             80.00  1974/01/08  1974/01/08 17:09    40  *   FILE 547
//*   BSPSGLBL           80.00  1974/01/23  1974/01/23 14:03     6  *   FILE 547
//*   DBGMSG             80.01  1974/01/29  1974/01/29 12:57    14  *   FILE 547
//*   DO                 80.03  1974/01/21  1974/01/24 15:11   157  *   FILE 547
//*   ELSE               80.00  1974/01/24  1974/01/24 15:11    53  *   FILE 547
//*   ELSEIF             80.00  1974/01/24  1974/01/24 15:12    89  *   FILE 547
//*   ENDDO              80.00  1974/01/24  1974/01/24 15:12    66  *   FILE 547
//*   ENDIF              80.00  1974/01/24  1974/01/24 15:12    53  *   FILE 547
//*   EXIT               80.00  1974/01/24  1974/01/24 15:13    68  *   FILE 547
//*   FC                 80.00  1974/01/23  1974/01/23 21:43    18  *   FILE 547
//*   FILL                                                          *   FILE 547
//*   IEECODES           80.01  1974/01/16  1974/01/16 21:11    40  *   FILE 547
//*   IF                 80.00  1974/01/24  1974/01/24 15:13    83  *   FILE 547
//*   IFERR                                                         *   FILE 547
//*   IFGLO                                                         *   FILE 547
//*   IFPRO                                                         *   FILE 547
//*   IHAIQE             80.01  1974/01/18  1974/01/18 13:08    24  *   FILE 547
//*                                                                 *   FILE 547
//*           LOAD      -  Load Library in TSO XMIT format          *   FILE 547
//*                                                                 *   FILE 547
//*   Contents of LOAD member:                                      *   FILE 547
//*                                                                 *   FILE 547
//*   BRODSCAN                   1974/03/24                         *   FILE 547
//*   BSPAPFCK                   1974/03/24                         *   FILE 547
//*   BSPAPFLS                   1974/03/24                         *   FILE 547
//*   BSPFCOOK                   1974/03/24 REFR RENT               *   FILE 547
//*   BSPOSCMD                   1974/03/24 REFR RENT               *   FILE 547
//*   BSPPA2SI                   1974/03/24 REFR RENT               *   FILE 547
//*   BSPPILOT                   1974/03/24                         *   FILE 547
//*   BSPRUNSC                   1974/03/24 REFR RENT               *   FILE 547
//*   BSPSETPF                   1974/03/24                         *   FILE 547
//*   BSPVTMWT                   1974/03/23                     AC  *   FILE 547
//*   CBT973                     1974/03/17                         *   FILE 547
//*   COOKIE            *ALIAS   1974/03/24 REFR RENT  BSPFCOOK     *   FILE 547
//*   DELAY                      1974/03/24                         *   FILE 547
//*   DISKMAP                    1974/02/07                     AC  *   FILE 547
//*   DISKMAPA                   1974/02/07                     AC  *   FILE 547
//*   FCOOKIE           *ALIAS   1974/03/24 REFR RENT  BSPFCOOK     *   FILE 547
//*   FORTUNE           *ALIAS   1974/03/24 REFR RENT  BSPFCOOK     *   FILE 547
//*   MOVELOAD                   1974/03/24                     AC  *   FILE 547
//*   MOVELOD           *ALIAS   1974/03/24            MOVELOAD AC  *   FILE 547
//*   MURPHY            *ALIAS   1974/03/24 REFR RENT  BSPFCOOK     *   FILE 547
//*   REQUEUE                    1974/03/24                     AC  *   FILE 547
//*   SMPTFSEL                   1974/03/24                         *   FILE 547
//*   TAPEHDR                    1974/03/24                         *   FILE 547
//*                                                                 *   FILE 547
//*           CMDSBSYS  -  CMD Subsystem Load Modules in TSO XMIT   *   FILE 547
//*                        format                                   *   FILE 547
//*                                                                 *   FILE 547
//*     - - - - - - - - - - - - - - - - - - - - - - - - - - - -     *   FILE 547
//*                                                                 *   FILE 547
//*      I have fixed a few bugs in the collection, and provided    *   FILE 547
//*      a few more utilities.  The new utilities included are:     *   FILE 547
//*                                                                 *   FILE 547
//*      BSPAPFLS - List the APF datasets.  This is also            *   FILE 547
//*                 integrated into BSPILOT                         *   FILE 547
//*      BSPOSCMD - Run OS commands from batch or STC               *   FILE 547
//*      BSPPA2SI - JCL PARM to SysIn processor, takes JCL parm     *   FILE 547
//*                 and makes it available in dataset for next      *   FILE 547
//*                 step                                            *   FILE 547
//*      MOVELOAD - Preload IEHMOVE modules for improved            *   FILE 547
//*                 performance                                     *   FILE 547
//*      REQUEUE  - requeue current job for later re-execution      *   FILE 547
//*      BRODSCAN - Analyse SYS1.BRODCAST                           *   FILE 547
//*      DELAY    - Lets job wait for a specified time              *   FILE 547
//*      TAPEHDR  - display tape label info                         *   FILE 547
//*                                                                 *   FILE 547
//*      The modules beginning with BSP.. have been written by      *   FILE 547
//*      me, whereas the others were sent to me by        .         *   FILE 547
//*      somitcw@yahoo.com for inclusion in the Turnkey System.     *   FILE 547
//*                                                                 *   FILE 547
```
