import mysql.connector
from conecta_db import mydb


mycursor = mydb.cursor()

mycursor.execute('create database if not exists cadastro_usuario')

mycursor.execute('use cadastro_usuario')

mycursor.execute('create table if not exists login  (usuario varchar(20) primary key, '
                 'senha varchar(20) not null, email varchar(55) not null)')

def verificar_usuario(usuario, senha):
    mycursor = mydb.cursor()
    sql = "select * from login WHERE usuario = %s and senha = %s"
    val = (usuario, senha)
    mycursor.execute(sql, val)
    # mycursor.execute(f'select usuario from login where usuario = {usuario} and senha = {senha} ')
    mycursor.fetchall()
    rc = mycursor.rowcount
    if rc == 1:
        return True
    else:
        return False



def consulta_usuario():

    mycursor = mydb.cursor()
    mycursor.execute('use cadastro_usuario')

    print('='*50)
    print('BEM VINDO AO SISTEMA'.center(50))
    print('='*50)

    opt = int(input(
        '''         DIGITE A OPÇÃO DESEJADA:
        [1] -> Acesso ao Banco de Dados.
        [2] -> Cadastrar Usuario e Senha.
        [3] -> Lembrar Senha.
        [4] -> Sair 
        ->   ''' ))

    if opt == 1:
        usuario = input('Digite o seu usuario [letra minuscula]: ').strip().lower()
        senha = input('Digite a sua senha: ').strip()
        resp = verificar_usuario(usuario, senha)
        if resp == True:
            return True
        else:
            print('Digite um usuario cadastrado!')
            consulta_usuario()
    elif opt == 2:
        pass
