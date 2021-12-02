# SL
imports system.console
Module Module1

    Sub Main()
        Dim dice As Integer
        dim board(100) as string
        rollingdice(dice)
        displayingboard(board)
        Console.ReadKey()
    End Sub

    Sub rollingdice(ByRef x As Integer)
        Randomize()
        x = Int(Rnd() * 6) + 1
        Console.WriteLine(x)
    End Sub
    
    sub displayingboard(ByRef x() As String)
        For i = 1 To x.Length - 1
            If x(i) <> "" Then
                ForegroundColor = ConsoleColor.Green
            Else
                ForegroundColor = ConsoleColor.Gray
            End If
            Console.Write("[{0:00}] ", i)
            If i Mod 10 = 0 Then
                Console.WriteLine()
            End If
        Next
        Console.WriteLine()

    End Sub
End Module
