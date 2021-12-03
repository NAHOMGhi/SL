Imports System.Console
Module Module1
    Public Class player
        Public colour As String
        Public number As Integer
    End Class

    Sub Main()
        createplayer()
        Dim dice As Integer
        Dim board(100) As String
        Dim gameover = False
        Do
            rollingdice(dice)
            displayingboard(board)
        Loop Until gameover = False
        Console.ReadKey()
    End Sub

    Function rollingdice(ByRef x As Integer)
        Randomize()
        x = Int(Rnd() * 6) + 1
        Return x
    End Function
    Sub createplayer()
        For counter = 0 To 3
            Dim player1 As New player
            player1.number = 1
            Dim choice As String
            Dim validcolour As Boolean = True
            Console.WriteLine("Colour : ")
            choice = Console.ReadLine()
            Do
                Try
                    Console.ForegroundColor = choice
                    player1.colour = choice
                    validcolour = True
                Catch ex As Exception
                    Console.WriteLine("Not a valid colour")
                End Try
            Loop Until validcolour = True
        Next

    End Sub
    Sub displayingboard(ByRef x() As String)
        For i = 1 To x.Length - 1
            If i <> 4 Then
                Console.Write("[{0:00}] ", i)
            Else
                Console.Write("[Ls] ")
            End If
            If i Mod 10 = 0 Then
                Console.WriteLine()
            End If
        Next
        Console.WriteLine()

    End Sub

End Module
