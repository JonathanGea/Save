using System;

namespace _8Mentri
{
    static int N = 8;
    static int k = 1;

    /*Fungsi utilitas untuk mencetak solusi */
    static void printSolution(int[,] board)
    {
        
        for (int i = 0; i < N; i++)
        {
            for (int j = 0; j < N; j++)
                Console.Write(" {0} ", board[i, j]);
            Console.Write("\n");
        }
        Console.Write("\n");
    }
    static bool isSafe(int[,] board, int row, int col)
    {
        int i, j;

        /*  Periksa baris ini di sisi kiri */
        for (i = 0; i < col; i++)
            if (board[row, i] == 1)
                return false;

        /* Periksa diagonal atas di sisi kiri */
        for (i = row, j = col; i >= 0 && j >= 0; i--, j--)
            if (board[i, j] == 1)
                return false;

        /* Periksa diagonal bawah di sisi kiri */
        for (i = row, j = col; j >= 0 && i < N; i++, j--)
            if (board[i, j] == 1)
                return false;

        return true;
    }
    static bool solveNQUtil(int[,] board, int col)
    {
        /* Fungsi utilitas rekursif untuk memecahkan masalah N Queen */
        // jika kita sudah mengisi semua kolom
        if (col == N)
        {
            printSolution(board);
            return true;
        }

        /* Pertimbangkan kolom ini dan coba tempatkan ratu ini di semua baris satu per satu */
        // mengulangi setiap baris dalam kolom
        bool res = false;
        for (int i = 0; i < N; i++)
        {
            /*Periksa apakah ratu dapat ditempatkan
            papan [i, col] */
            if (isSafe(board, i, col))
            {
                /* Tempatkan ratu ini di papan [i, col] */
                board[i, col] = 1;

                // Jadikan hasil benar jika ada penempatan
                // adalah mungkin
                res = solveNQUtil(board, col + 1) || res;
                //letakkan ratu di posisi yang sesuai jika aman, dengan memperbarui matriks dengan 1
                // periksa apakah ada kemungkinan pengaturan untuk posisi ratu saat ini di kolom

                /*Jika menempatkan ratu di papan [i, col]
                tidak mengarah ke solusi, lalu
                keluarkan ratu dari papan [i, col] */
                board[i, col] = 0; // BACKTRACK; MUNDUR
                // jika tidak ada pengaturan yang mungkin ditemukan maka mundur dan singkirkan ratu
            }
        }

        /* Jika ratu tidak bisa ditempatkan di baris manapun
            kolom ini kolom kemudian mengembalikan salah*/
        return res;
        //kembali jika mengulangi setiap baris tanpa menemukan solusi apa pun
    }
    public static void Main()
    {
        int[,] board = new int[N, N];

        if (solveNQUtil(board, 0) == false)
        {
            Console.Write("Solution does not exist");
            return;
        }

        return;
    }

  
}
