Module Module1

    Sub Main()


        Dim yayılım As Long = 0
        Console.WriteLine("İlk gün COVID19 tanısı konmuş hasta sayısı: ")
        Dim deger1 As Long = Convert.ToInt32(Console.ReadLine())
        Console.WriteLine("Kaçıncı gün için vaka sayısını öğrenmek istiyorsunuz: ")
        Dim deger2 As Long = Convert.ToInt32(Console.ReadLine())
        Dim deger6 As Long = 0


        Console.WriteLine("Hastalığın yayılma süreci boyunca hastalık 1 kişiden kaç kişiye bulaşmıştır" &
                          vbCrLf & "1.Seçenek = 1 kişiye bulaşmıştır" &
                          vbCrLf & "2.Seçenek = 10 kişiye bulaşmıştır " &
                          vbCrLf & "(1. Seçeneği seçmek için '1' tuşuna 2.Seçeneği seçmek için '2' tuşuna basınız)")

        Dim d3 As Integer = Convert.ToInt32(Console.ReadLine())



        If d3 = 1 Then
            yayılım = 1
        ElseIf d3 = 2 Then
            yayılım = 10
        End If

        Dim deger4 As Long = deger1
        Dim deger4_1 As Long = deger1
        Dim deger5 As Long = deger1
        Console.WriteLine(("1. Gün sonunda " + Convert.ToString(deger1) + " kişi hasta") & vbCrLf&)
        For gun = 2 To deger2


            If gun >= 15 Then

                deger4 *= yayılım  'seçilen seçeneğe göre hastalığın toplam kaç kişiye yayılacağını buluyoruz
                If gun > 15 Then
                    deger4 = deger4 - deger5
                End If
                Console.WriteLine(Convert.ToString(gun) + ". Gün sonunda Toplam hasta sayısı = " + Convert.ToString((deger4 + deger4_1) - deger5) + " kişi" &
                                      vbCrLf & "iyileşen toplam hasta sayısı = " + Convert.ToString(deger5) & vbCrLf&)
                deger6 = deger4_1
                deger4_1 += deger4
                deger4 += deger6


                If yayılım = 1 Then
                    deger5 *= 2

                ElseIf yayılım = 10 Then
                    deger5 *= 11
                End If



                GoTo deger9

            End If
            deger4 *= yayılım  'seçilen seçeneğe göre hastalığın toplam kaç kişiye yayılacağını buluyoruz
            Console.WriteLine(Convert.ToString(gun) + ". Gün sonunda Toplam vaka sayısı = " + Convert.ToString(deger4 + deger4_1) + " kişi" & vbCrLf&)
            deger6 = deger4_1
            deger4_1 += deger4
            deger4 += deger6
deger9:


        Next


        Console.WriteLine("Çıkmak için bir tuşa basınız")
        Console.ReadKey()


    End Sub
End Module
