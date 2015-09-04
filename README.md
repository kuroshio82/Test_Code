# Test_Code
// This is the README File
// Ruby File to create a hash with movies and edit them
movies = {
    "Fight Club".to_sym => 4,
    "Memento".to_sym => 3,
    "Lord of War".to_sym => 2
}

puts "What would you like to do?"
choice = gets.chomp

case choice
when "add"
  puts "Enter a movie title:"
  title = gets.chomp
  puts "Enter a movie rating:"
  rating = gets.chomp
  if movies[title.to_sym] == nil
      movies = { 
      title.to_sym => rating.to_i
      }
      puts "Movie added!"
  else
      puts "Movie already exists!"
  end
  
when "update"
  puts "Enter a movie title:"
  title = gets.chomp
  if movies[title.to_sym] == nil
      puts "Movie does not exist!"
  else
      puts "Enter a movie rating:"
      rating =  gets.chomp
      movies = {
          title.to_sym => rating.to_i
      }
      puts "Movie rating updated!"
  end
  
when "display"
  movies.each do |movie, rate|
      puts "#{movie}: #{rate}"
  end
  
when "delete"
  puts "Enter a movie title to delete:"
  title = gets.chomp
  if movies[title.to_sym] == nil
      puts "Movie does not exist!"
  else 
      movies.delete(title)
      puts "Movie was deleted!"
  end  
  
else
  puts "Error, command not recognized!"
end
