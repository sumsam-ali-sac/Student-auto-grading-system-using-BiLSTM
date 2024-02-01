# Introduction

In today's fast-paced world, technology has become an integral part of every aspect of our lives, including education. As technology continues to advance, the need for efficient and accurate evaluation of student performance has become increasingly important. With this in mind, the development of a student auto-grading system using advanced techniques like BiLSTM and DeBERTa can help educators provide timely and constructive feedback to their students.

The BiLSTM (Bidirectional Long Short-Term Memory) model is a powerful deep learning algorithm that is widely used in natural language processing tasks, including sentiment analysis and machine translation. This model can capture the context of words in a sentence and provide a better understanding of the relationships between them.

On the other hand, DeBERTa (Decoding-enhanced Bidirectional Encoder Representations from Transformers) is a state-of-the-art transformer-based model that has shown great success in various natural language processing tasks, including text classification, named entity recognition, and question-answering.

By combining the strengths of these models, we can create a student auto-grading system that can accurately assess student work and provide feedback promptly. The system can be designed to analyze and grade various types of student work, including essays, reports, and multiple-choice exams.

To ensure that the system is accessible and easy to use for educators, we can incorporate an FTP (File Transfer Protocol) server using the pyftplib library. The FTP server can be used to store and retrieve student work, allowing educators to easily upload and download assignments as needed. This can also help streamline the grading process, as educators can easily access student work and provide feedback in a centralized location.

The importance of a student auto-grading system lies in its ability to provide timely and accurate feedback to students, which can help them identify areas for improvement and ultimately improve their academic performance. Additionally, such a system can help reduce the workload on educators, allowing them to focus on providing more personalized instruction to their students.

In conclusion, a student auto-grading system using advanced techniques like BiLSTM and

DeBERTa, along with an FTP server using pyftplib, can greatly enhance the efficiency and effectiveness of the grading process. By providing accurate and timely feedback to students, we can help them achieve academic success and reach their full potential.

# Methodology

Data Preprocessing: The first step in developing a student auto-grading system is to preprocess the data. This involves cleaning and formatting the data to ensure that the model can properly analyze it. For instance, if the system is designed to grade essays, the text may need to be converted to a standardized format and any irrelevant information removed. Additionally, the data may need to be tokenized and vectorized, so that it can be processed by the deep learning models.

![](https://www.dropbox.com/s/8veeyp91a6n1c2c/Picture1.jpg?dl=0)

BiLSTM Model: The BiLSTM model is a powerful deep learning algorithm that can be used for various natural language processing tasks, including text classification and sentiment analysis. In the context of a student auto-grading system, the BiLSTM model can be used to analyze student work and provide feedback. The model can be trained on a dataset of previously graded student work, to accurately identify and grade key features of the work.


DeBERTa Model: The DeBERTa model is a state-of-the-art transformer-based model that has shown great success in various natural language processing tasks. In the context of a student auto-grading system, the DeBERTa model can be used to analyze the context and meaning of the text, providing a deeper understanding of the relationships between words and phrases. This can help improve the accuracy of the grading process, as the model can better identify the intent and meaning behind the student's work.


can help streamline the grading process, as educators can easily access student work and provide feedback in a centralized location.

Integration: The final step in developing a student auto-grading system is to integrate the different components into a cohesive system. This involves combining the BiLSTM and DeBERTa models with the FTP server and developing a user-friendly interface for educators to interact with the system. The system can be designed to grade various types of student work, including essays, reports, and multiple-choice exams, providing timely and accurate feedback to students to help them improve their academic performance.

# Architecture

FTP Server side:

We created an FTP server with a graphical user interface (GUI) to select the server directory and start the server. The program uses several Python modules, such as os, tkinter, and pyftpdlib, to create the FTP server and the GUI.

The MyFTPHandler class is a subclass of the FTPHandler class from the pyftpdlib module. It sets the current working directory to the user's desktop when the user connects to the server.

The start\_ftp\_server() function creates an instance of the DummyAuthorizer class from the pyftpdlib module. It reads user information from two files, students.txt and teachers.txt, and creates users with limited and full permissions, respectively. It also creates two additional users with full permissions. The function then sets the authorizer for the MyFTPHandler class and creates an instance of the ThreadedFTPServer class from the pyftpdlib module. It sets the maximum number of connections and the maximum number of connections per IP address.

Finally, it starts the server using the serve\_forever() method.

The select\_directory() function opens a file dialog window to allow the user to select a directory. It then changes the current working directory to the selected directory, writes the directory path to a file, and updates the text of the directory\_path\_label.

The main part of the program creates a GUI using the Tkinter module. It sets the geometry, background color, and title of the window. It also defines the font styles and colors for the labels and buttons. It creates a label for the "Server Directory" text and another label for the directory path. It creates two buttons for selecting the directory and starting the server, respectively. Finally, it starts the GUI using the mainloop() method.

![Picture1](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/e3ee94ba-6a62-478a-aa5b-1c2aa06d93e8)

FTP client is implemented using the ftplib library.

The program defines two classes: FTPClient and FTPClientGUI. The FTPClient class defines methods to connect to an FTP server, upload and download files, and list the files on the server. The FTPClientGUI class defines the graphical user interface and uses an instance of the FTPClient class to perform the actual FTP actions.

Here are the details of the program:

The program imports the necessary libraries: ftplib, os, csv, and tkinter.

The FTPClient class is defined. It has four attributes: host, port, user, password, and ftp. The \_\_init\_\_ method initializes these attributes, and the connect, disconnect, upload, download, and list\_files methods perform the corresponding FTP actions.

The FTPClientGUI class is defined. It takes two arguments: master, which is the main window of the GUI, and client, which is an instance of the FTPClient class. It defines a method read\_users\_from\_file that reads the usernames, passwords, and permissions from two files, "students.txt" and "teachers.txt", and returns a list of dictionaries.

The \_\_init\_\_ method of the FTPClientGUI class creates the graphical user interface. It creates labels and entry fields for the host, port, username, and password, as well as a "Connect" button. It also creates a label to display the connection status. When the "Connect" button is clicked, it calls the connect method of the FTPClient instance to establish a connection to the FTP server.

The FTPClientGUI class also creates a new window for the FTP actions. It creates labels and entry fields for the local and remote file paths, as well as the "Upload", "Download", and "List Files" buttons. When these buttons are clicked, they call the corresponding methods of the FTPClient instance to perform the corresponding FTP actions.

When the professor logins, he has permission to download and grade essays all at once

![Picture8](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/2121353b-2930-4eab-b1c9-07c9e6bffa62)


When Student logins, he has the permission to only upload

![Picture7](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/317e0054-5d8f-4da2-b3d1-fcd59f1b8d7b)


Density of grade distribution:

![Picture5](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/8310ae6d-fd9e-4a57-8e3b-5573525986f6)

Correlation Graph:

![Picture4](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/372c8e32-256a-4faa-872e-e8c09d9188e0)

# Process

1. Server is Started after selecting Directory:

![Picture3](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/612e98f7-6f42-4a41-aebb-d32f3f5f72d4)
![Picture9](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/1b6c85a0-a4db-407b-ae34-e4ea7684cc99)


2. Student logins and uploads his essay

![Picture7](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/a57ad954-9238-4f2e-a5fd-1f54de663325)

2. Teacher logins and can grade, upload, and download essays

![Picture8](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/54745d9b-b305-4b83-aed8-0d70e5ebb1e4)

3. Sample essay's text is extracted via OCR

![Picture10](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/b88e41ed-ec8c-4748-8eae-285fa17927cc)

![Picture11](https://github.com/sumsam-ali-sac/Student-auto-grading-system-using-BiLSTM/assets/93638623/b02343ab-1a72-4890-997e-efeec70b71b5)

# Conclusion

The development of a student auto-grading system using advanced techniques like BiLSTM and DeBERTa, along with an FTP server using pyftplib, offers significant benefits in the field of education. By leveraging deep learning models, such as BiLSTM and DeBERTa, the system can accurately assess and provide timely feedback on various types of student work, including essays, reports, and multiple-choice exams. The integration of an FTP server simplifies the process of uploading and downloading student assignments, making the system user-friendly for educators. The student auto-grading system enhances the efficiency and effectiveness of the grading process, providing accurate feedback to students for their academic improvement while reducing the workload on educators.

References:

1. Hochreiter, S., & Schmidhuber, J. (1997). Long short-term memory. Neural Computation, 9(8), 1735-1780.
2. He, L., Zhang, Q., Ren, S., & Sun, J. (2020). DeBERTa: Decoding-enhanced BERT with Disentangled Attention. arXiv preprint arXiv:2006.03654.
3. Mockus, J., Wang, Y., Wu, S., & Zhang, H. (2021). FTP Attack and Defense: A Machine Learning Approach. IEEE Access, 9, 13189-13203.
4. Python Software Foundation. (n.d.). pyftplib: FTP client library for Python. Retrieved from https://github.com/giampaolo/pyftpdlib

