#include <stdio.h>
#include <stdlib.h>

#define MAX_STUDENTS 5
#define MAX_SUBJECTS 3

int main() {
    char names[MAX_STUDENTS][50];
    int scores[MAX_STUDENTS][MAX_SUBJECTS];
    int total[MAX_STUDENTS] = {0};

    // Input: Get student names and scores
    for (int i = 0; i < MAX_STUDENTS; i++) {
        printf("Enter name for student %d: ", i + 1);
        scanf("%s", names[i]);

        printf("Enter scores for %d subjects:\n", MAX_SUBJECTS);
        for (int j = 0; j < MAX_SUBJECTS; j++) {
            printf("  Subject %d: ", j + 1);
            scanf("%d", &scores[i][j]);
            total[i] += scores[i][j];
        }
    }
    printf("\n%-15s", "Student Name");
    for (int j = 0; j < MAX_SUBJECTS; j++) {
        printf("Subject %d\t", j + 1);
    }
    printf("Total Marks\n");

    for (int i = 0; i < MAX_STUDENTS; i++) {
        printf("%-15s", names[i]);
        for (int j = 0; j < MAX_SUBJECTS; j++) {
            printf("%d\t\t", scores[i][j]);
        }
        printf("%d\n", total[i]);
    }
    #ifdef _WIN32
        system("pause");
    #endif

    return 0;
}
