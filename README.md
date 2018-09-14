# 09-goemetry-101-alechavez26
09-goemetry-101-alechavez26 created by GitHub Classroom
/*  Alejandra Chávez Cruz
 * 13/sept/2018
 * A01411970@itesm.mx
 */
#include <stdio.h>
#include <math.h>

//These is my main menu.
char  main_Menu(){
    char options;

    printf("\nThese are your options:\n");
    printf("1. Perimeter.\n");
    printf("2. Surface.\n");
    printf("3. Volume.\n");
    printf("4. Exit.\n");
    printf("Which one would you like to know?");

    scanf(" %c", &options);

    return options;
}

// Menu for perimeters
char perMenu(){
    char choice;

    printf("\nThese are your options:\n");
    printf("1. Square.\n");
    printf("2. Rectangle.\n");
    printf("3. Triangle.\n");
    printf("4. Exit.\n");
    printf("Which one would you like to know?");

    scanf(" %c", &choice);
    return choice;
}

// Menu for surface
char surfMenu() {
    char choice;

    printf("\nThese are your options:\n");
    printf("1. Square.\n");
    printf("2. Rectangle.\n");
    printf("3. Triangle.\n");
    printf("4. Exit.\n");
    printf("Which one would you like to know?");

    scanf(" %c", &choice);
    return choice;
}

// Menu for volume
char volMenu(){
    char options;

    printf("\nThese are you options:\n");
    printf("1. Cube.\n");
    printf("2. Rectangular prism.\n");
    printf("3. Pyramid.\n");
    printf("4. Exit.\n");
    printf("Which one would you like to know?");

    scanf(" %c", &options);
    return options;
}

// Menu for square perimeter.
void squarePerimeter_Menu(){
    float l;

    printf("\nSquare\n");
    printf("Give me the size of one side:");
    scanf("%f", &l);
    printf("The perimeter of the square is: %.2f\n", 4*l);
}

// Menu for rectangle perimeter.
void rectanglePerimeter_Menu(){
    float length;
    float width;

    printf("\nRectangle\n");
    printf("Give me the length and width (please insert a coma between them) :");
    scanf("%f, %f", &length, &width);
    printf("The perimeter of the rectangle is: %.2f\n", 2*length + 2*width);
}

// Menu for triangle perimeter.
void trianglePerimeter_Menu(){
    float l;

    printf("\nTriangle\n");
    printf("Give me the size of one of the sides:");
    scanf("%f", &l);
    printf("The perimeter of the triangle is: %.2f\n", 3*l);
}

// Menu for square perimeter.
void squareSurface_Menu(){
    float l;

    printf("\nSquare\n");
    printf("Give me the side of one side:");
    scanf("%f", &l);
    printf("The surface of the square is: %.2f\n", l*l);
}

// Menu for rectangle surface.
void rectangleSurface_Menu(){
    float length;
    float width;

    printf("\nRectangle\n");
    printf("Give me the length and the width (separated by a coma):");
    scanf("%f, %f", &length, &width);
    printf("The surface of the rectangle is: %.2f\n", length * width);
}

// Menu for triangle surface.
void triangleSurface_Menu(){
    float l;

    printf("\nTriangle\n");
    printf("Give me the size of one of the sides");
    scanf("%f", &l);
    printf("The surface of the triangle is: %.2f\n", sqrt(3) / 4 * l * l);
}

// Menu for the volume of the cube.
void sVolume_Menu(){
    float side;

    printf("\nCube\n");
    printf("Give me one side:");
    scanf("%f", &side);
    printf("The volume of the cube is: %.2f\n", pow(side, 3));
}

// Menu for the volume of the rectangular prism.
void rVolume_Menu(){
    float length;
    float width;
    float height;

    printf("\nRectangle\n");
    printf("Give me the length, width and height (separated by a coma):");
    scanf("%f, %f, %f", &length, &width, &height);
    printf("The volume of the rectangular prism is: %.2f\n", length * width * height);
}

// Menu for the pyramid prism
void tVolume_Menu(){
    float side;
    float height;

    printf("\nPyramid\n");
    printf("Give me one side and the height (separated by a coma):");
    scanf("%f, %f", &side, &height);
    printf("The volume of the pyramid is: %.2f\n", side * side * height / 3);
}


void Perimeter(){
    printf("\nPerimeter\n");

    char options;

    do{
        options = perMenu();

        switch(options) {
            case '1':
                squarePerimeter_Menu();
                options = '4';
                break;
            case '2':
                rectanglePerimeter_Menu();
                options = '4';
                break;
            case '3':
                trianglePerimeter_Menu();
                options = '4';
                break;
            case '4':
                break;
            default:
                printf("Not valid. Try again.\n");
                break;
        }
    } while(options != '4');

}


void Surface(){
    printf("\nSurface\n");

    char options;

    do{
        options = surfMenu();

        switch(options) {
            case '1':
                squareSurface_Menu();
                options = '4';
                break;
            case '2':
                rectangleSurface_Menu();
                options = '4';
                break;
            case '3':
                triangleSurface_Menu();
                options = '4';
                break;
            case '4':
                break;
            default:
                printf("Not valid. Try again.\n");
                break;
        }
    } while(options != '4');

}


void Volume(){
    printf("\nVolume\n");

    char options;

    do{
        options = volMenu();

        switch(options) {
            case '1':
                sVolume_Menu();
                options = '4';
                break;
            case '2':
                rVolume_Menu();
                options = '4';
                break;
            case '3':
                tVolume_Menu();
                options = '4';
                break;
            case '4':
                break;
            default:
                printf("OH NO. Try again.\n");
                break;
        }
    } while(options != '4');

}

int main() {
    char options;


    do{
        options = main_Menu();

        switch(options){
            case '1':
                Perimeter();
                break;
            case '2':
                Surface();
                break;
            case '3':
                Volume();
                break;
            case '4':
                break;
            default:
                printf("Your choice is not valid.\n");
                break;
        }
    } while(options != '4');

    return 0;
}
