# phonebook_linkedlist_file_SDL_image_C

This is a Phonebook program that records contacts by first name, last name, and phone number.

This program utilizes an external .txt file to save or load list of contacts. The loading of contacts are done using function
in the beginning of the program and to save any new contacts or editting of contact list requires user to run the save function,
that will overwrite the .txt file. Aside from using files, within the C program itself, the stores data of contacts using a 
linked list of struct that contains character type of first name, last name, and phone number. Linked list is used as the number
of data are undefined thus cannot be limited using array, also linked list would operate better for sorting the data.

The list of functions in the C program are:

int menuMain(): This function basically shows the main menu of the whole program. It is consist of 7 part, add contact, delete contact 
  sort contact, insert picture, display contact, search contact, and save file. We also create a submenu in delete
  (int menuDelete();) , search (int menuSearch();) , and sort contact (int menuSort();) because we want the user to
  delete, search, and sort, not only using the first name, but they can also use the last name or even the number.

void displayContact(): This function is to open the saved file from what we have added before, or even the file that we have saved
   using the .txt file which we can save through the saveFile() function. This function also able to display
   the picture from the folder using .bmp file and using image*insertnumber*.bmp which we are using the openPicture()
   function.

int addContact(): This function is to add the contact using char fname (for the firstname), char lname (last name), and char
    phone(phone number). In this function we basically using the linked list process to create the list of contact
    into the txt file which we must save it first using the saveFile(). Then we also ask the user to input the pic
    -ture using the .bmp file that the user must copy to the designated folder using the image%d format.

void openPicture(): This function is used for utilizing the SDL image external library to display image of the contact. It locates the .BMP
  image file and display it within the determined window for user to see if they display contact. The external library is obtained from 
  https://www.libsdl.org/download-2.0.php while the program is altered from the original program of http://gigi.nullneuron.net/gigilabs/displaying-an-image-in-an-sdl2-window/.

void searchFirst(), void searchLast(), void searchNum(): This function serves to search a specific contact based on first name, last
  name, or phone number. It is done by reading through the linked list until the value matched. Since the data type array of char is used
  for all the data then a string compare could easily be used to match the data. However, the search is case sensitive due to string compare.

void deleteFirst(), void deleteLast(), void deleteNum(): This function serves to delete a specific contact based on first name, last
  name, or phone number. The principle of searching for the contact to delete is the same as the search function however after a search is done
  the matching contact should be removed by isolating it unto a temporary struct and allocating previous contact to the next contact then 
  releasing the temporary struct.

void sortFirst(), void sortLast(), void sortNum(): The sorting functions are seperated into three type based on the first name,
  last name, and phone number. The principle of sorting used is that a single run is done for reading the linked list until the NULL
  terminal value. However to ensure the sorting is thorough, each time a string compare of the value of two linked list are no according
  to accending sorting then the position of both the linked list are switch and the program runs the sorting starting from the head of the
  linked list again such that when all is in order the looping ends. Function is of void type and no return value is required.

int loadFile(): This function is to open the .txt file with the saved contact list, in this case is phonebookTEST.txt.
  This function runs by looping of reading the file data onto a initialized string and then string copied unto the new initiliazed 
  linked list struct. Then after creating the linked list, the .txt file is closed. The function is of int type as a return value is
  required for the program to know how many linked list data are there.

void saveFile(): This function is a loop that runs through the linked list and fprintf unto the .txt file each data (first name, last name,
  and phone number). This function is void as it require no return value. 

int isEmpty(): This function is to check whether the linked list is empty or already has a value so that when user wants to delete or search
  or sort an empty list, it would just inform user that the list is empty without wasting time running other function.


This program incorporated a SDL image thus require SDL for those who does not have it. It allows the program to display picture for each contact
if the user manually insert it with the required name in the folder of the C project. There are still some unprecise outcome for image since the 
program deadline approaches, however this is what has been developed for the project.
