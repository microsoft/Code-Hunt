Code Hunt data release 1

Directory layout:

README.txt - this file
solutions/
        SectorN-LevelM.cs - reference solution for sector N, level M
        SectorN-LevelM.challengeId - REST API challengeId for sector N, level M
users/
        UserNNN/ - folder for user #NNN, users in order of decreasing score
                experience - user-reported experience level, 1-3:
                                1="Beginner", 2="Intermediate", 3="Advanced"
                SectorN-LevelM/
                        attemptNNN-YYYYMMDD-HHMMSS[-winningR].(java|cs) -
                                Submission #NNN by user, submitted on date
                                YYYY-MM-DD at time HH:MM:SS. "-winningR"
                                is included for an attempt which won the
                                level with rating R (a number 1-3 where 3 is
                                the best). Submissions may be in Java or C#;
                                different attempts on the same level may be in
                                different languages.


Notes on interpreting the data:

The 24 levels are grouped into 4 sectors of 6 levels each. A user may only
access a level in a sector if they have won at least all but one of the levels
in the previous sector.

Selecting a level results in the most recent attempt being submitted
automatically. The first time a level is selected, this will be the default
program for the level which usually is just the proper signature with
"return 0;" or similar. This means that all of the first attempts on a given
puzzle are likely identical for every user.

Attempts may be repeated. Some users sometimes hit the submit button/key combo
multiple times in a row, which is recorded as multiple submissions.
