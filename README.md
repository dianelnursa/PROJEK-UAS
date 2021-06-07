import java.util.Scanner;

public class komplit {

    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        //memasukan awalan
        System.out.println("============================= NILAI PRAKTIKUM ALPRO 1B ==============================");
        String ulang;
        System.out.print("Nama operator penginput : ");
        String nama = input.nextLine();
        System.out.print("NIM operator penginput  : ");
        Double nim = input.nextDouble();
        System.out.println("=========================");

        /*memasukan data yang ingin ditampilkan pada tabel*/
        do {
            System.out.print("\nMasukan Jumlah Data : ");
            int n = input.nextInt();
            System.out.println("---------------------");

            String mhs[] = new String[n];
            String status[] = new String[n];
            String grade[] = new String[n];
            int UTS[] = new int[n];
            int UAS[] = new int[n];
            int PROJEK[] = new int[n];
            int total[] = new int[n];
            int rata[] = new int[n];

            for (int i = 0; i < n; i++) {
                input.nextLine();
                System.out.print("\nNama mahasiswa : ");
                mhs[i] = input.nextLine();
                System.out.print("Nilai UTS : ");
                UTS[i] = input.nextInt();
                System.out.print("Nilai UAS : ");
                UAS[i] = input.nextInt();
                System.out.print("Nilai PROJEK : ");
                PROJEK[i] = input.nextInt();

                if (UTS[i] >= 0 && UTS[i] <= 100 && UAS[i] >= 0 && UAS[i] <= 100 && PROJEK[i] >= 0 && PROJEK[i] <= 100) {
                    total[i] = (UTS[i] + UAS[i] + PROJEK[i]);
                    rata[i] = (UTS[i] + UAS[i] + PROJEK[i]) / 3;
                    if (rata[i] >= 90) {
                        grade[i] = "A";
                        status[i] = "Lulus";
                    } else if (rata[i] >= 80 && rata[i] <= 89) {
                        grade[i] = "B";
                        status[i] = "Lulus";
                    } else if (rata[i] >= 70 && rata[i] <= 79) {
                        grade[i] = "C";
                        status[i] = "Lulus";
                    } else {
                        grade[i] = "D";
                        status[i] = "Tidak Lulus";
                    }
                }
            }
            //menampilkan awalan
            System.out.println("\n==========================================================================================================");
            System.out.println("Operator : " + nama.toLowerCase());
            System.out.println("============================================================================================================");
            System.out.println("|                                           NILAI ALPRO 1B                                                 |");
            System.out.println("============================================================================================================");
            System.out.println("No\tNama\t\tUTS\tUAS\tTugas Akhir\tTotal\tRata-rata\tGrade\tStatus");

            //menampilkan data
            for (int a = 0; a < n; a++) {
                System.out.println((a + 1) + "\t" + mhs[a].toUpperCase() + "\t" + UTS[a] + "\t" + UAS[a]
                        + "\t" + PROJEK[a] + "\t\t" + total[a] + "\t" + rata[a] + "\t\t" + grade[a] + "\t" + status[a]);
            }
            System.out.println("============================================================================================================");
            //memasukan penutup
            System.out.print("Apakah Ingin Mengulang (y/n) : ");
            ulang = input.next();

        } //menampilkan penutup
        while (ulang.equalsIgnoreCase("y"));
    }
}
