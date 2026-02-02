# BIOLOGY-HEART-SIMULATION-
C#
using System;
using System.Threading;

namespace BiologyHeartProgram
{
    class Heart
    {
        public int HeartRate { get; set; }

        public Heart(int rate)
        {
            HeartRate = rate;
        }

        public void HeartInfo()
        {
            Console.WriteLine("\n--- HUMAN HEART INFORMATION ---");
            Console.WriteLine("• The human heart is a muscular organ.");
            Console.WriteLine("• It pumps blood throughout the body.");
            Console.WriteLine("• It has four chambers.");
            Console.WriteLine("• Average heart rate: 72 BPM\n");
        }

        public void ShowStructure()
        {
            Console.WriteLine("\n--- HEART STRUCTURE ---");
            Console.WriteLine("1. Right Atrium  (Deoxygenated blood)");
            Console.WriteLine("2. Right Ventricle (To lungs)");
            Console.WriteLine("3. Left Atrium   (Oxygenated blood)");
            Console.WriteLine("4. Left Ventricle (To body)");
        }

        public void BloodFlow()
        {
            Console.WriteLine("\n--- BLOOD CIRCULATION PROCESS ---");
            Console.WriteLine("Body → Right Atrium");
            Pause();
            Console.WriteLine("Right Atrium → Right Ventricle");
            Pause();
            Console.WriteLine("Right Ventricle → Lungs");
            Pause();
            Console.WriteLine("Lungs → Left Atrium");
            Pause();
            Console.WriteLine("Left Atrium → Left Ventricle");
            Pause();
            Console.WriteLine("Left Ventricle → Body");
        }

        public void HeartBeat()
        {
            Console.WriteLine("\n--- HEART BEAT SIMULATION ---");
            for (int i = 1; i <= 6; i++)
            {
                Console.WriteLine("Lub ❤️  (Systole)");
                Pause();
                Console.WriteLine("Dub 💙  (Diastole)");
                Pause();
            }
        }

        public void PulseRate()
        {
            Console.WriteLine("\n--- PULSE RATE ---");
            Console.WriteLine("Heart Rate: " + HeartRate + " beats per minute");

            if (HeartRate < 60)
                Console.WriteLine("Condition: Low heart rate (Bradycardia)");
            else if (HeartRate > 100)
                Console.WriteLine("Condition: High heart rate (Tachycardia)");
            else
                Console.WriteLine("Condition: Normal heart rate");
        }

        private void Pause()
        {
            Thread.Sleep(800);
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Heart heart = new Heart(72);

            while (true)
            {
                Console.Clear();
                Console.WriteLine("❤️ BIOLOGY HEART SIMULATION PROGRAM ❤️");
                Console.WriteLine("-------------------------------------");
                Console.WriteLine("1. Heart Information");
                Console.WriteLine("2. Heart Structure");
                Console.WriteLine("3. Blood Circulation");
                Console.WriteLine("4. Heart Beat Simulation");
                Console.WriteLine("5. Pulse Rate Analysis");
                Console.WriteLine("6. Exit");
                Console.Write("\nEnter your choice: ");

                int choice = int.Parse(Console.ReadLine());

                switch (choice)
                {
                    case 1:
                        heart.HeartInfo();
                        break;
                    case 2:
                        heart.ShowStructure();
                        break;
                    case 3:
                        heart.BloodFlow();
                        break;
                    case 4:
                        heart.HeartBeat();
                        break;
                    case 5:
                        heart.PulseRate();
                        break;
                    case 6:
                        Console.WriteLine("Exiting program...");
                        return;
                    default:
                        Console.WriteLine("Invalid choice!");
                        break;
                }

                Console.WriteLine("\nPress any key to continue...");
                Console.ReadKey();
            }
        }
    }
}
#OUTPUTS
