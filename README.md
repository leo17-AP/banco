# leonardo
#Start code here
import time
resp = "si"
sep = "-"*40
while resp == "si":
  print("-----Bienvenido-al-menú-bancario------")
  print("¿Qué tipo de movimiento desea realizar?")
  print("1) Movimiento en efectivo")
  print("2) Movimiento con tarjeta")
  opcion = str(input("Elija:").lower())
  print(sep)
  if opcion == "1":
    resp2 = "si"
    for i in range(resp2 == "si"):
      print("--------Movimientos-en-efectivo-------")
      print("¿Qué tipo de acción desea realizar?")
      print("a)Pago de servicios")
      print("b)Pago de tarjetas de credito")
      accion = str(input("Elija:").lower())
      if accion == "a":
        print("--------Pago-de-servicios-------")
        print("1) Agua")
        print("2) Luz")
        print("3) Teléfono")
        print("4) Otro...")
        servicios = str(input("Elija:"))
        if servicios == "1" or servicios == "2" or servicios == "3" or servicios == "4":
          if servicios == "1":
            servicio = "Agua"
          elif servicios == "2":
            servicio = "Luz"
          elif servicios == "3":
            servicio = "Teléfono"
          else:
            servicio = str(input("Ingrese el nombre del servicio que desea pagar :").lower())
          convenio = int(input("Ingrese el número de convenio :"))
          monto = float(input("Ingrese el monto que pagara :"))
          if monto > 0:
            efectivo = float(input("Ingrese el efectivo con el que pagara:"))
            if efectivo >= 0:
              print("Espere", end="")
              for i in range(1, 9):
                print(".",end="") # your own code
                time.sleep(0.5)
              print("   \nlistones pa los moños :)")
              cambioefectivo = monto - efectivo
              comprobanteEfectivo = str(input("Desea imprimir su comprobante (si/no):").lower())
              if comprobanteEfectivo == "si":
                print("|-----------------------------------------------------------------|") # your own code
                print("|SERVICIO--NO.CONVENIO--MONTO A PAGAR--EFECTIVO INGRESADO--CAMBIO-|") # your own code
                print("|",servicio,"\t",convenio,"\t",monto,"\t",efectivo,"\t",cambioefectivo,"|") # your own code
                print("|-----------------------------------------------------------------|") # your own code
              elif comprobanteEfectivo == "no":
                print("")
                resp2 = str(input("¿Desea-realizar-otra-accion?").lower())
              else:
                print("Efectivo ingresado menor al monto que se desea pagar o invalido")
                resp2 = str(input("¿Desea-intentar-de-nuevo?").lower())
          else:
            print("Monto ingresado invalido")
        else:
          print("Servicio seleccionado invalido")
        print(sep)
        resp2 = str(input("¿Desea-realizar-otra-accion?").lower())
      elif accion == "b":
        contadordigitos = 0
        print("------Pago-de-tarjetas-de-credito-------")
        print(sep)
        numtarjeta = str(input("Ingrese el número de la tarjeta[8 números]: "))
        for i in numtarjeta:
          contadordigitos += 1
        if contadordigitos == 8:
          monto = float(input("Ingrese el total a pagar: "))
          print("Espere", end="")
          if monto > 0:
            for i in range(1, 9):
              print(".",end="") # your own code
              time.sleep(0.5)
            print("")
            print("Listo")
            efectivo = float(input("Ingrese el efectivo con el que pagara: "))
            if efectivo >= monto:
              cambioefectivo = monto - efectivo
              comprobanteEfectivo = str(input("Desea imprimir su comprobante (si/no):").lower())
              if comprobanteEfectivo == "si":
                print("|-----------------------------------------------------------------|") # your own code
                print("|--NO. De Tarjeta--MONTO A PAGAR--EFECTIVO INGRESADO--CAMBIO------|") # your own code
                print("|--",numtarjeta,"\t","\t",monto,"\t","\t",efectivo,"\t","\t",cambioefectivo,"|") # your own code
                print("|-----------------------------------------------------------------|") # your own code
              elif comprobanteEfectivo == "no":
                print("")
                resp2 = str(input("¿Desea-realizar-otra-accion?").lower())
              else:
                print("")
                print("Opcion invalida")
                resp2 = str(input("¿Desea-realizar-otra-accion?").lower())
            else:
              print("Efectivo ingresado menor al monto que se desea pagar o invalido")
          else:
            print("Monto ingresado invalido")
        else:
          print("Tarjeta ingresada invalida")
        resp2 = str(input("¿Desea-realizar-otra-accion?").lower())
      else:
        print("------------Opción-invalida------------")
        resp2 = str(input("¿Desea-intentar-de-nuevo?").lower())
      resp = resp2
  elif opcion == "2":
    resp2 = "si"
    for i in range(resp2 == "si"):
      print("----------Movimientos--con-tarjeta---------")
      tarjeta = int(input("Ingrese el numero de tarjeta[8 dígitos enteros]: "))
      print("Espere", end="")
      for i in range(1, 9):
        print(".",end="") # your own code
        time.sleep(0.5)
      print("")
      print("")
      print("listo")
      if tarjeta == 12345678 or tarjeta == 87654321 or tarjeta == 12348765 or tarjeta == 11112222:
        if tarjeta == 12345678:
          nip = 1234
          nombre = "leo"
          saldodisponible = 1500
        elif tarjeta == 87654321:
          nip = 4321
          nombre = "yair"
          saldodisponible = 1000
        elif tarjeta == 12348765:
          nip = 2143
          nombre = "ckan"
          saldodisponible = 2000
        else:
          nip = 1122
          nombre = "fragoso"
          saldodisponible = 500
        Ingresenip = int(input("Ingrese su NIP: "))
        print("")
        if Ingresenip == nip:
          print("Bienvenido", nombre)
          print("")
          print("¿Que tipo de acción desea realizar?")
          print("a)Consultar saldo")
          print("b)retiro de efectivo")
          print("c)Pago de servicios")
          print("")
          accion = str(input("Elija:").lower())
          print("")
          if accion == "a":
            print("Hola, ", nombre)
            print("")
            print("Tu saldo disponible es de :", saldodisponible)
            comprobanteTarjeta = str(input("Desea imprimir comprobante: ").lower())
            print("")
            if comprobanteTarjeta == "si":
              print("Nombre","---","Saldo-Disponible") # your own code
              print(nombre,"-",saldodisponible) # your own code
            elif comprobanteTarjeta == "no":
              resp2 = str(input("¿Desea-realizar-alguna-otra-acción?").lower())
            else:
              print("Respuesta invalida")
              resp2 = str(input("¿Desea-intentar-de-nuevo?").lower())
          elif accion == "b":
            print("Hola, ", nombre)
            print("")
            print("Tu saldo disponible es de :", saldodisponible)
            print("")
            retiro = float(input("Ingresa que cantidad de dinero deseas retirar"))
            print("Espere", end="")
            for i in range(1, 9):
              print(".",end="") # your own code
              time.sleep(0.5)
            print("")
            print("")
            print("listo")
            print("")
            if saldodisponible >= retiro:
              saldonuevo = saldodisponible - retiro
              print(nombre, "tu nuevo saldo disponible es de : ", saldonuevo)
              comprobanteTarjeta = str(input("Desea imprimir comprobante: ").lower())
              if comprobanteTarjeta == "si":
                print("")
                print("Nombre","Saldo-Antiguo","Dinero-Retirado","Saldo-nuevo") # your own code
                print(nombre,"---",saldodisponible,"---",retiro,"---",saldonuevo) # your own code
                print("")
              elif comprobanteTarjeta == "no":
                resp2 = str(input("¿Desea-realizar-alguna-otra-acción?").lower())
              else:
                print("Opcion ingresada invalida")
                resp2 = str(input("¿Desea-intentar-de-nuevo?").lower())
            elif saldodisponible < retiro:
              print("No cuentas con saldo suficiente para retirar")
          elif accion == "c":
            print("Bienvenido: ", nombre, "tu saldo disponible es de :", saldodisponible)
            print("--------Pago-de-servicios-------")
            print("1) Agua")
            print("2) Luz")
            print("3) Teléfono")
            print("4) Otro...")
            servicios = str(input("Elija:"))
            if servicios == "1" or servicios == "2" or servicios == "3" or servicios == "4":
              if servicios == "1":
                servicio = "Agua"
              elif servicios == "2":
                servicio = "Luz"
              elif servicios == "3":
                servicio = "Teléfono"
              else:
                servicio = str(input("Ingrese el nombre del servicio que desea pagar :").lower())
              convenio = int(input("Ingrese el número de convenio :"))
              monto = float(input("Ingrese el monto que va a pagar"))
              cotinuar = str(input("¿Deseas continuar con la acción?"))
              if cotinuar == "si":
                if saldodisponible >= monto:
                  saldonuevo = saldodisponible - monto
                  print("Espere", end="")
                  for i in range(1, 9):
                    print(".",end="") # your own code
                    time.sleep(0.5)
                  print("")
                  print("")
                  print("listo")
                  print("")
                  print(nombre, " su servicio se ha pagado")
                  print("")
                  comprobanteTarjeta = str(input("Desea imprimir comprobante: ").lower())
                  if comprobanteTarjeta == "si":
                    print("|-----------------------------------------------------------------|") # your own code
                    print("|SERVICIO--NO.CONVENIO--MONTO A PAGAR--SALDO ANTIGUO--SALDO NUEVO-|") # your own code
                    print("|",servicio,"\t----",convenio,"\t----",monto,"\t----",saldodisponible,"\t----",saldonuevo,"|") # your own code
                    print("|-----------------------------------------------------------------|") # your own code
                  elif comprobanteTarjeta == "no":
                    resp2 = str(input("¿Desea-realizar-alguna-otra-acción?").lower())
                  else:
                    print("Acción ingresada invalida")
                    resp2 = str(input("¿Desea-intentar-de-nuevo?").lower())
                elif saldodisponible >= monto:
                  print("Saldo insuficiente")
                  resp2 = str(input("¿Deseas-realizar-alguna-otra-accion?").lower())
              elif cotinuar == "no":
                resp2 = str(input("¿Deseas-realizar-alguna-otra-accion?").lower())
              else:
                print("Acción ingresada invalida")
                resp2 = str(input("¿Desea-intentar-de-nuevo?").lower())
          else:
            print("Acción ingresada invalida")
            resp2 = str(input("¿Desea-intentar-de-nuevo?").lower())
          print("")
          resp2 = str(input("¿Desea-realizar-otro-movimiento?").lower())
        else:
          print("NIP ingresado invalido")
          resp2 = str(input("¿Desea-intentar-de-nuevo?").lower())
      else:
        print("Tarjeta ingresada invalida")
        resp2 = str(input("¿Desea-intentar-de-nuevo?").lower())
      print("")
      resp = resp2
  else:
    print("------------Opción-invalida------------")
    resp = str(input("¿Desea-intentar-de-nuevo?").lower())
    print(sep)
print("Gracias por usar el programa hasta luego")
