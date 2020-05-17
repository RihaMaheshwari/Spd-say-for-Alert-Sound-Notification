# **Spd-say for Alert Sound Notification**
spd-say sends text-to-speech output request to speech-dispatcher process which handles it and ideally outputs the result to the audio system.

## **Speech Dispatcher**

Speech-dispatcher is a server process that is responsible for  transforming  requests  for text-to-speech  output  into  actual  speech  hearable  in  the  speakers.  It  arbitrates concurrent speech requests based on message priorities,  and  abstracts  different  speech synthesizers.  Client  programs,  like  screen readers or navigation software, send speech requests to speech-dispatcher using TCP protocol (with  the  help  of  client  libraries).

Speech-dispatcher  is  usually started automatically by client libraries (i.e. autospawn), so you only need to run it manually if testing/debugging, or when in other  explicit  need for a special setup.

### **Use-case**

There are multiple ways this can be used but most common usecase is to get an alert. This can be in Linux when your long Job/Process is completed.

# **Install Speech Dispatcher**
```
$ sudo apt-get install speech-dispatcher
```
### **Run spd-say**
```
#Spd-say
spd-say "Your Job is Completed!!"
#Execute Command
command ; spd-say "Task Completed"
```

You can also make an alias, by adding the following lines in .bashrc file.

```
#Alias
alias alert='spd-say "Task Completed"'
#Use alert when you want to get notified
command ; alert

```
