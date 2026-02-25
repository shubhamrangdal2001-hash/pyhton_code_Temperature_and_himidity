# gandhinagar_weather_analysis.py

import csv
from statistics import mean, median

def load_weather_data(filename):
    temperatures = []
    humidities = []
    aqi_values = []

    with open(filename, mode='r') as file:
        reader = csv.DictReader(file)
        for row in reader:
            temperatures.append(float(row['temperature']))
            humidities.append(float(row['humidity']))
            aqi_values.append(float(row['aqi']))

    return temperatures, humidities, aqi_values


def calculate_stats(data_list):
    avg = mean(data_list)
    med = median(data_list)
    return avg, med


def save_results_to_file(results_text, output_filename):
    with open(output_filename, 'w') as file:
        file.write(results_text)


def main():
    input_file = "gandhinagar_weather.csv"
    output_file = "weather_analysis_results.txt"

    temperatures, humidities, aqi_values = load_weather_data(input_file)

    avg_temp, median_temp = calculate_stats(temperatures)
    avg_humidity, median_humidity = calculate_stats(humidities)
    avg_aqi, median_aqi = calculate_stats(aqi_values)

    results = (
        "Gandhinagar Weather & AQI Analysis (Last 10 Days)\n"
        "-------------------------------------------------\n"
        f"Average Temperature: {avg_temp:.2f} °C\n"
        f"Median Temperature: {median_temp:.2f} °C\n\n"
        f"Average Humidity: {avg_humidity:.2f} %\n"
        f"Median Humidity: {median_humidity:.2f} %\n\n"
        f"Average AQI: {avg_aqi:.2f}\n"
        f"Median AQI: {median_aqi:.2f}\n"
    )

    print(results)

    save_results_to_file(results, output_file)
    print(f"Results successfully saved to '{output_file}'")


if __name__ == "__main__":
    main()
