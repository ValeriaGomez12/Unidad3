import netmiko
from netmiko import ConnectHandler
sshCli = ConnectHandler(
        device_type='cisco_ios',
        host='10.10.20.70',
        port=2231,
        username='admin',
        password='admin'
        )
output = sshCli.send_command("show ip int brief", read_timeout = 10, expect_string = r"#")
print ("show ip int brief:\n{}\n".format(output))
#print(output)


config_commands = [
    'int loopback 1'
    'ip add <<<<<: 2.2.2.2 255.255.255.0'
    'Prueba loboratorio 2'
    ]
output = sshCli.send_config_set(config_commands, read_timeout = 10, expect_string = r"#")
#print (output)