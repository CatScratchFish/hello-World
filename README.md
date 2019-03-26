static void Main(string[] args)
        {
            string Userlnput;
            while(true)
            {
                try
                {
                    Console.Write("Input a number between 0 and 5 "+"(or just hit return exit)>");
                    Userlnput = Console.ReadLine();
                    if (Userlnput == "")
                        break;
                    int index = Convert.ToInt32(Userlnput);
                    if (index < 0 || index > 5)
                        //抛出异常IndexOutIfRangeException
                        throw new IndexOutOfRangeException("You typed in" + Userlnput);
                    Console.WriteLine("Your number was"+index );
                }
                catch(IndexOutOfRangeException e)
                {
                    Console.WriteLine("Exception:"+"Number should be between 0 and 5. "+e.Message);
                }
                catch (Exception e)
                {
                    Console.WriteLine("An exception was thrown . Message was ."+e.Message);
                }
                catch
                {
                    Console.WriteLine("Some other exception has occurred");
                }
                finally
                {
                    Console.WriteLine("Thank you");
                    Console.Read();
                }
