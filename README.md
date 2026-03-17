import psutil
import time

CPU_THRESHOLD = 80
MEMORY_THRESHOLD = 80

def monitor():
    print("Monitoring started...")

    while True:
        cpu = psutil.cpu_percent()
        memory = psutil.virtual_memory().percent

        print(f"CPU: {cpu}%, Memory: {memory}%")

        if cpu > CPU_THRESHOLD:
            print("ALERT: High CPU Usage!")

        if memory > MEMORY_THRESHOLD:
            print("ALERT: High Memory Usage!")

        time.sleep(2)

if __name__ == "__main__":
    monitor()
