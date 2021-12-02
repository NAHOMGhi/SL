# SL

Module Module1

    Sub Main()
        Dim dice As Integer
        rollingdice(dice)
        Console.ReadKey()
    End Sub

    Sub rollingdice(ByRef x As Integer)
        Randomize()
        x = Int(Rnd() * 6) + 1
        Console.WriteLine(x)

    End Sub
End Module
