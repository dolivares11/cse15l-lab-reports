# Week 3 Lab Report

## Part 1
{
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    int num = 0;
    ArrayList<String> list = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Number: %d", num);
        } else if (url.getPath().equals("/increment")) {
            num += 1;
            return String.format("Number incremented!");
        } else {
            System.out.println("Path: " + url.getPath());
            if (url.getPath().contains("/add")) {
                String[] parameters = url.getQuery().split("=");
                if(parameters[0].equals("s")) {
                    list.add(parameters[1]);
                    return "added " + list.get(list.size()-1) + "\n size: " + list.size();
                }
            }
            else if(url.getPath().contains("/search")) {
                String[] parameters2 = url.getQuery().split("=");
                if(parameters2[0].equals("s")) {
                    String word = parameters2[1];
                    ArrayList<String> storeWords = new ArrayList<String>();
                    for(int j = 0; j < list.size(); j++) {
                            int nump = list.get(j).indexOf(word);
                            System.out.println(nump);
                            if(nump != -1) {
                                storeWords.add(list.get(j));
                                System.out.println("TRUE");
                            }
                    }
                    return "These are the words with the substring of " + parameters2[1] +": " + storeWords.toString();
                }
            }
            return "404 Not Found!";
        }
    }
}

class SearchEngine {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

}
## Part 2