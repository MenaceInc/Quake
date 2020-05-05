cmake_minimum_required(VERSION 3.0)
project(Quake C ASM)

add_executable(winquake WIN32)
target_compile_options(winquake PRIVATE
                       $<$<COMPILE_LANGUAGE:ASM>:-x assembler-with-cpp>
                       )

target_compile_features(winquake PRIVATE
                        c_std_90
                        )

target_include_directories(winquake PRIVATE
                           WinQuake/scitech/INCLUDE
                           )

target_link_directories(winquake PRIVATE
                        WinQuake/scitech/LIB/WIN32/VC
                        )
target_link_libraries(winquake PRIVATE
                      MGLLT
                      winmm
                      dxguid
                      wsock32
                      )

# Program icon
target_sources(winquake PRIVATE
               WinQuake/winquake.rc
               )

# OS specific
target_sources(winquake PRIVATE
               WinQuake/cd_win.c
               WinQuake/conproc.c
               WinQuake/in_win.c
               WinQuake/net_win.c
               WinQuake/net_wins.c
               WinQuake/net_wipx.c
               WinQuake/snd_win.c
               WinQuake/sys_win.c
               WinQuake/sys_wina.s
               WinQuake/vid_win.c
               )

# OS agnostic sources
target_sources(winquake PRIVATE
               WinQuake/chase.c
               WinQuake/cl_demo.c
               WinQuake/cl_input.c
               WinQuake/cl_main.c
               WinQuake/cl_parse.c
               WinQuake/cl_tent.c
               WinQuake/cmd.c
               WinQuake/common.c
               WinQuake/console.c
               WinQuake/crc.c
               WinQuake/cvar.c
               WinQuake/d_draw.s
               WinQuake/d_draw16.s
               WinQuake/d_edge.c
               WinQuake/d_init.c
               WinQuake/d_modech.c
               WinQuake/d_part.c
               WinQuake/d_parta.s
               WinQuake/d_polysa.s
               WinQuake/d_polyse.c
               WinQuake/d_scan.c
               WinQuake/d_scana.s
               WinQuake/d_sky.c
               WinQuake/d_spr8.s
               WinQuake/d_sprite.c
               WinQuake/d_surf.c
               WinQuake/d_vars.c
               WinQuake/d_varsa.s
               WinQuake/draw.c
               WinQuake/host.c
               WinQuake/host_cmd.c
               WinQuake/keys.c
               WinQuake/math.s
               WinQuake/mathlib.c
               WinQuake/menu.c
               WinQuake/model.c
               WinQuake/net_dgrm.c
               WinQuake/net_loop.c
               WinQuake/net_main.c
               WinQuake/net_vcr.c
               WinQuake/pr_cmds.c
               WinQuake/pr_edict.c
               WinQuake/pr_exec.c
               WinQuake/r_aclip.c
               WinQuake/r_aclipa.s
               WinQuake/r_alias.c
               WinQuake/r_aliasa.s
               WinQuake/r_bsp.c
               WinQuake/r_draw.c
               WinQuake/r_drawa.s
               WinQuake/r_edge.c
               WinQuake/r_edgea.s
               WinQuake/r_efrag.c
               WinQuake/r_light.c
               WinQuake/r_main.c
               WinQuake/r_misc.c
               WinQuake/r_part.c
               WinQuake/r_sky.c
               WinQuake/r_sprite.c
               WinQuake/r_surf.c
               WinQuake/r_varsa.s
               WinQuake/sbar.c
               WinQuake/screen.c
               WinQuake/snd_dma.c
               WinQuake/snd_mem.c
               WinQuake/snd_mix.c
               WinQuake/snd_mixa.s
               WinQuake/surf16.s
               WinQuake/surf8.s
               WinQuake/sv_main.c
               WinQuake/sv_move.c
               WinQuake/sv_phys.c
               WinQuake/sv_user.c
               WinQuake/view.c
               WinQuake/wad.c
               WinQuake/world.c
               WinQuake/worlda.s
               WinQuake/zone.c
               )
