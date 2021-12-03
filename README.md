Imports System.Console
Module Module1
    Public Class player ' PLayer class-stores their colour, number and place
        Public colour As String
        Public number As Integer
        Public place As Integer
    End Class

    Sub Main() 'Main function
        createplayer()
        Dim dice As Integer
        Dim board(100) As String
        Dim gameover = False
        Do 'Gmae loop-where all functions will be called repeatdely as game goes on

            displayingboard(board)

        Loop Until gameover = False ' loop until game is over/finishes
        Console.ReadKey()
    End Sub
    'I removed the rolling dice function and instead added it within move sub

    Sub createplayer() 'Creates new players via the class then assigns them their place on the baord(0)
        Dim player1, player2, player3, player4 As New player
        Dim players As New List(Of player)({player1, player2, player3, player4})
        For counter = 0 To 3

            players(counter).place = 0
            players(counter).number = counter + 1

            Dim choice As String
            Dim validcolour As Boolean = True
            Console.WriteLine("Colour : ")
            choice = Console.ReadLine()
            Do
                Try
                    Console.ForegroundColor = choice
                    players(counter).colour = choice
                    validcolour = True
                Catch ex As Exception
                    Console.WriteLine("Not a valid colour")
                End Try
            Loop Until validcolour = True
        Next

    End Sub
    Sub move(ByRef player As Object)
        Randomize()
        Dim x As Integer = Int(Rnd() * 6) + 1
        player.place = player.place + x



    End Sub
    Sub displayingboard(ByRef x() As String)
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
