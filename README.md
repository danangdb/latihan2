mkdir data # membuat folder dengan nama data
cd data # merubah direktori ke folder data
wget https://github.com/labusiam/dataset/raw/main/weather_data.xlsx # impor data excel
in2csv weather_data.xlsx --sheet "weather_2014" > weather_2014.csv #melalukan convert sheet weather_2014 dan menyimpannya pada file weather_2014.csv
in2csv weather_data.xlsx --sheet "weather_2015" > weather_2015.csv #melalukan convert sheet weather_2014 dan menyimpannya pada file weather_2015.csv
csvstack weather_2014.csv weather_2015.csv > weather.csv # menggabungkan data weather_2014.csv dan weather_2015.csv , menyimpan dengan nama weather.csv
rm weather_data.xlsx #menghapus file 
cat weather.csv | sample -r 0.3 > sample_weather.cs #melakukan sampling 
