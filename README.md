# Nested-Loop 
print("Starting steps: 1800")
    epMotion.DosingMotor.GotoPos(currentPos + 1800)

    from together import *
    get_cameraimage()
    get_finalimage()
    i=0
    if get_finalimage.c==1.50:
        print("Desired diameter of drop obtained: ", get_finalimage.c)
    #elif():
        #while get_finalimage.c<float(1.50):
            #i=i+100
            #print("Increasing the step size..", "i= ",100, "Steps: ", (2000+i))
            #epMotion.DosingMotor.GotoPos(currentPos + (2000+i))
            #time.sleep(3)
            #get_camera()
            #get_finalimage()
            #if get_finalimage.c == float(1.50):
                #print("The desired diamter of the drop obtained")
    else:
        while get_finalimage.c > 1.50:
            i = i + 200
            #print("After incrementation of 100 i become: ", i)
            print("Decreasing step size..", "i= ", 200, "Steps: ", (1800 - i))
            epMotion.DosingMotor.GotoPos(currentPos + (1800 - i))
            time.sleep(1)
            get_cameraimage()
            get_finalimage()
            if get_finalimage.c == 1.50:
                print("Desired diameter of drop obtained: ", get_finalimage.c)
                break
        else:
            i=1800-i
            print("******************* The value of steps from last case *****************************:", i)
            while get_finalimage.c < 1.50:
                i = i+100
                #print("After incrementation of 50 i become: ", i)
                print("Increasing step size..", "i= ", 100, "New steps: ", i)
                j = i
                #print("2000-i: ", j)
                epMotion.DosingMotor.GotoPos(currentPos + j )
                time.sleep(1)
                get_cameraimage()
                get_finalimage()
                if get_finalimage.c == 1.50:
                    print("Desired diameter of drop obtained: ", get_finalimage.c)
                    break
            else:
                i=j
                print("***************** The value of steps from last case ******************************:", i)
                while get_finalimage.c > 1.50:
                    i = i-50
                    #print("After incrementation of 50 i become: ", i)
                    print("Decreasing step size..", "i= ", 50, "New steps: ",i)
                    j = i
                    #print("2000-i: ", j)
                    epMotion.DosingMotor.GotoPos(currentPos + j )
                    time.sleep(1)
                    get_cameraimage()
                    get_finalimage()
                    if get_finalimage.c == 1.50:
                        print("Desired diameter of drop obtained: ", get_finalimage.c)
                        break
                    #elif get_finalimage.c == 1.51:
                        #print("Desired approximate diameter of drop obtained: ", get_finalimage.c)
                        #break
                else:
                    i=j
                    print("************** The value of steps from last case ******************************:", i)
                    while get_finalimage.c < 1.50:
                        i = i + 20
                        #print("After incrementation of 10 i become: ", i)
                        print("Increasing step size..", "i= ", 20, "New steps: ", i)
                        j = i
                        #print("2000-i: ", j)
                        epMotion.DosingMotor.GotoPos(currentPos + j )
                        time.sleep(1)
                        get_cameraimage()
                        get_finalimage()
                        if get_finalimage.c == 1.50:
                            print("Desired diameter of drop obtained: ", get_finalimage.c)
                            break
                    else:
                        #print("Desired approximate diameter of drop obtained: ", get_finalimage.c)
                        i = j
                        print("************** The value of steps from last case ******************************:", i)
                        while get_finalimage.c > 1.50:
                            i = i - 5
                            #print("After decrementation of 10 i become: ", i)
                            print("Decreasing step size..", "i= ", 5, "New steps: ", i)
                            j = i
                            # print("2000-i: ", j)
                            epMotion.DosingMotor.GotoPos(currentPos + j)
                            time.sleep(1)
                            get_cameraimage()
                            get_finalimage()
                            if get_finalimage.c == 1.50:
                               print("Desired diameter of drop obtained: ", get_finalimage.c)
                               break
                        else:
                            i = j
                            print("************** The value of steps from last case ******************************:",i)
                            while get_finalimage.c < 1.50:
                                i = i + 2
                                # print("After decrementation of 10 i become: ", i)
                                print("Increasing step size..", "i= ", 2, "New steps: ", i)
                                j = i
                                # print("2000-i: ", j)
                                epMotion.DosingMotor.GotoPos(currentPos + j)
                                time.sleep(1)
                                get_cameraimage()
                                get_finalimage()
                                if get_finalimage.c == 1.50:
                                    print("Desired diameter of drop obtained: ", get_finalimage.c)
                                    break
                            else:
                                print("Desired approximate diameter of drop obtained: ", get_finalimage.c)
                            #break
    epMotion.ComfortApi.EjectTipIntoWaste()
    count = count + 1
    print("the value of count is: ", count)
print("loop finished")
exit(1)
