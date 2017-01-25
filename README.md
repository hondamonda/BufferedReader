# BufferedReader
read File from comp

    public static void readFile(String fileName) {
        try {
            // Exceptions could be thrown below
            FileInputStream fis = new FileInputStream(fileName);
            BufferedReader br = new BufferedReader(
              new InputStreamReader(fis));
            String line = null;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            br.close();
            fis.close();
        } catch (FileNotFoundException e) {
            // Exception handler for FileNotFoundException
            // We just inform the client that there is
            // not such file
            System.out.println("The file \"" + fileName +
              "\" does not exist! Unable to read it.");
        } catch (IOException e) {
            // Exception handler for IOException
            e.printStackTrace();
        }
    }
