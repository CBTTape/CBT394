# CBT394
Converted to GitHub via [cbt2git](https://github.com/wizardofzos/cbt2git)

This is still a work in progress. 
Due to amazing work by Alison Zhang and Jake Choi repos are no longer deleted.

```
//***FILE 394 is from Jan Jakubek of Toronto, Ontario, Canada.        * FILE 394
//*                                                                   * FILE 394
//*               .--------------------------------.                  * FILE 394
//*               |  CBT TAPE - Index of file 394  |                  * FILE 394
//*               |  From: Jan (Janek) Jakubek     |                  * FILE 394
//*               '--------------------------------'                  * FILE 394
//*                                                                   * FILE 394
//*    KSDSPACE  VSAM KSDS space use mapping utility (reports on      * FILE 394
//*              space used by data records, free space, # of index   * FILE 394
//*              records per IX level, low/high key per control       * FILE 394
//*              area, unused space due to IX record too short).      * FILE 394
//*                                                                   * FILE 394
//*    KSDSPACO  Older version of KSDSPACE. Should run on             * FILE 394
//*              unsupported levels of DFSMS (1.2 or less). It does   * FILE 394
//*              not work with Extended Format/Addressability KSDS.   * FILE 394
//*                                                                   * FILE 394
//*    OFDVBFB   Converts sequential dataset from RECFM=VB to         * FILE 394
//*              RECFM=FB                                             * FILE 394
//*                                                                   * FILE 394
//*    LLAUPDTX  Synchronous LLA update routine (using LLACOPY        * FILE 394
//*              macro).  One member per step (specified in PARM)     * FILE 394
//*              gets refreshed.                                      * FILE 394
//*                                                                   * FILE 394
//*    LLAUPDTS  Synchronous LLA update routine (using LLACOPY        * FILE 394
//*              macro).  Multiple members (specified in SYSIN) get   * FILE 394
//*              refreshed.                                           * FILE 394
//*                                                                   * FILE 394
//*    DEFNVS    Generates IDCAMS DEFINE NONVSAM statements for a     * FILE 394
//*              DASD volume.                                         * FILE 394
//*                                                                   * FILE 394
//*    DELNVS    Generates IDCAMS DELETE NSCR statements for a        * FILE 394
//*              DASD volume.                                         * FILE 394
//*                                                                   * FILE 394
//*    IEFUSI    A sample, configurable (working in a real            * FILE 394
//*              production environment) SMF USI exit.                * FILE 394
//*                                                                   * FILE 394
//*    LDAPROBE  LDAP server probe REXX exec.                         * FILE 394
//*    LDAPROBJ  JCL (could run as an STC) to run LDAPROBE.           * FILE 394
//*                                                                   * FILE 394
//*    MXIVSTOR  Dispalys virtual storage usage of an address         * FILE 394
//*              space (REXX exec). Requires/ calls MXI to retrieve   * FILE 394
//*              foreign address space LDA/ASCB/RAX/RAXMEMLIMIT.      * FILE 394
//*              This is essentially a modified Mark Zelden's         * FILE 394
//*              REXXSTOR, except that input data from a foreign AS   * FILE 394
//*              are retrieved via MXI.                               * FILE 394
//*                                                                   * FILE 394
//*    TI        Displays RMM tape dataset info for an ISPF 3.4       * FILE 394
//*              dataset list entry using RMM LISTDATASET             * FILE 394
//*              subcommand (REXX exec).                              * FILE 394
//*                                                                   * FILE 394
//*    TV        Displays RMM tape volume info for an ISPF 3.4        * FILE 394
//*              dataset list entry using RMM VOLUME subcommand       * FILE 394
//*              (clist).                                             * FILE 394
//*                                                                   * FILE 394
//*    MAKENSWP  Makes all address spaces with same name              * FILE 394
//*              nonswappable.  This can be useful for Unix           * FILE 394
//*              applications (in our case CTG). Does this via MXI    * FILE 394
//*              MAKE command. This is a REXX exec.                   * FILE 394
//*                                                                   * FILE 394
//*    JJDGEN    Janek's data records generation utility. Need a      * FILE 394
//*              few records for testing of an application ? Try      * FILE 394
//*              this !                                               * FILE 394
//*                                                                   * FILE 394
//*    WTOH      Write Message to Operator routine (highlighted       * FILE 394
//*              messages).                                           * FILE 394
//*                                                                   * FILE 394
//*    $TABLES   See $TABLES doc member for description of general    * FILE 394
//*              purpose binary search table processing routines/     * FILE 394
//*              package.  This may be of interest for application    * FILE 394
//*              programmers (writing applications in PL/I, COBOL,    * FILE 394
//*              Assembler).                                          * FILE 394
//*                                                                   * FILE 394
//*    HALVE     Binary search tables processing subroutine           * FILE 394
//*                                                                   * FILE 394
//*    HLVTD     HALVE related macro: table definition                * FILE 394
//*                                                                   * FILE 394
//*    JJTBGEN   Create table to be searched/ processed by HALVE      * FILE 394
//*              subroutine.                                          * FILE 394
//*                                                                   * FILE 394
//*    TBLACCSS  Tables access interface routine for COBOL programs   * FILE 394
//*              (HALVE related).                                     * FILE 394
//*                                                                   * FILE 394
//*    KSDSINIT  New KSDS File Initialization Routine                 * FILE 394
//*                                                                   * FILE 394
//*    JJPDSD    Deletes all members of a PDS dataset. It is slow/    * FILE 394
//*              poor performer with PDS datasets, but it works       * FILE 394
//*              (better) with PDSE.                                  * FILE 394
//*                                                                   * FILE 394
//*    OFDASVER  Checks if specified address space/s is/are up.  If   * FILE 394
//*              all specified address spaces are up - ends with      * FILE 394
//*              return code of zero, otherwise ends with return      * FILE 394
//*              code of 16.                                          * FILE 394
//*                                                                   * FILE 394
//*              Possible use of this program:                        * FILE 394
//*              .Verify if a CICS or DBCOMM/DB region is up in the   * FILE 394
//*              first step of a job. If yes, continue the job,       * FILE 394
//*              otherwise terminate it.                              * FILE 394
//*                                                                   * FILE 394
//*              .Verify if all required STCs are up after IPL or     * FILE 394
//*              periodically throughout a day. If not - issue a      * FILE 394
//*              warning message.                                     * FILE 394
//*                                                                   * FILE 394
//*    Macros    SUBRET, SUBENT, TSTAMP, HLVTD                        * FILE 394
//*                                                                   * FILE 394
//*             Jan (Janek) Jakubek                                   * FILE 394
//*                                                                   * FILE 394
//*             Tel  :     416-255-8807      (Canada)                 * FILE 394
//*             Email:     Jan.Jakubek@CGI.COM                        * FILE 394
//*                                                                   * FILE 394
```
