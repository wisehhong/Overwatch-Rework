# Overwatch Rework Workshop

This repository contains Overwatch Workshop scripts used to prototype hero reworks.

## Table of Contents

- [Project Overview](#project-overview)
- [Repository Structure](#repository-structure)
- [Design Targets](#design-targets)
	- [Tanks](#tanks)
		- [Doomfist](#doomfist)
		- [Roadhog](#roadhog)
		- [Mauga](#mauga)
		- [Junker Queen](#junker-queen)
		- [Orisa](#orisa)
		- [D.Va](#dva)
	- [DPS](#dps)
		- [Junkrat](#junkrat)
		- [Echo](#echo)
		- [Sombra](#sombra)
		- [Venture](#venture)
		- [Soldier: 76](#soldier-76)
		- [Pharah](#pharah)
		- [Genji](#genji)
		- [Reaper](#reaper)
		- [Anran](#anran)
	- [Support](#support)
		- [Moira](#moira)
		- [Mercy](#mercy)
		- [Ana](#ana)
		- [Kiriko](#kiriko)
- [Notes](#notes)

## Project Overview

The goal of this project is to redesign heroes in ways that:
- Raise skill expression and decision-making depth.
- Reduce binary, low-counterplay interactions.
- Redistribute power from one-button outcomes into broader kit synergy.
- Preserve each hero's fantasy while improving gameplay health.

This repo is intended for rapid iteration in Workshop format so changes can be tested in-game and tuned over time.

## Repository Structure

- `doomfist.ow`: Current Workshop implementation for Doomfist rework logic.
- `variables.ow`: Player/global variable mapping reference used by Workshop scripts.

## Design Targets

### Tanks

#### Doomfist
> "Doomfist currently has too much power in his EMP Punch, being his primary engage and finishing tool in a hero otherwise lacking in the raw firepower to deal massive damage. Taking the power out of EMP Punch and into new abilities such as EMP Slam, Uppercut, and EMP Uppercut alleviates this, making him less binary over whether or not he hit a good EMP Punch or not, while still keeping the block -> charge loop necessary for Tank Doom."

- Hero health reduced from 525 to 450.
- New Ability: Rising Uppercut.
- Rising Uppercut cooldown: 6 seconds.
- Rising Uppercut knocks enemies slightly upward and away (out of Hand Cannon range).
- New Ability: Empowered Rising Uppercut (EMP Uppercut).
- EMP Uppercut functions as old Uppercut, knocking enemies upward and briefly movement-locking them.

Power Block:
- Block is immediately canceled after full charge.
- Full charge block does not reset cooldowns.
- Empowers your next Uppercut, Slam, or Rocket Punch.
- Empowerment is consumed as soon as one empowered ability is used.

Seismic Slam:
- Looking downward at a surface while mid-air enables Indicator Slam with gliding movement.

New Ability: Empowered Seismic Slam (EMP Slam):
- Functions as old Slam.
- Damage scales based on time spent slamming (50 to 100).

Rocket Punch:
- Empowered Punch keeps same charge speed, distance, and multi-punch hitbox as normal Rocket Punch.

Meteor Strike:
- Automatically empowers your next Uppercut, Slam, or Rocket Punch.
- Duration increased to 6 seconds.

The Best Defence...:
- Overhealth gained gradually instead of burst gain.

New Minor Perk: Anti-Air (replacing Survival of the Fittest):
- Hitting flying enemies with Uppercut, Seismic Slam, or Rocket Punch reduces their cooldown by 1 second.

New Major Perk: Rushdown (replacing Aftershock):
- Using an empowered ability without damaging any enemies keeps your gauntlet empowered.

#### Roadhog
> "Roadhog's main issues stem from how his Chain Hook is trivial to land at close range yet gives a massive reward nonetheless. Further, a lot of his optimal gameplay involves dealing massive damage to tanks such as Doomfist using his hook rather than going for more skillful backline hooks. Lastly, Roadhog struggles when he's not hitting his hook due to his range. Tightening his primary fire spread and adding additional distance to his secondary fire fixes this, while Hook now empowers your next primary fire based on the distance you pulled: allowing one-shots as long as they're earned. The addition of Pig Pen as a movement tool gives a much needed positioning vector to an otherwise grounded hero."

- Hero health reduced from 750 to 650.

Scrap Gun:
- Pellets reduced and primary spread tightened.
- No longer one-shots DPS/Support at close range.
- Added Shrapnel Launcher perk to base to increase secondary fire range.

Chain Hook:
- Cooldown reduced from 7 to 4 seconds.
- Increases next Scrap Gun primary fire damage based on pull distance (0 to 100% increase).
- Difficult, far-away hooks can grant one-shot combos.
- Post-hook stun duration reduced.

Take a Breather:
- Converted to cooldown ability (6 seconds).
- Grants slowly decaying overhealth instead of restoring health.

New Ability: Pig Pen:
- Cooldown: 12 seconds.
- Press Pig Pen key while trap is active to detonate it.
- Detonation damages and launches enemies upward.
- Also launches Roadhog (Junkrat mine-like movement tool).
- Requires short arming time before detonation.

#### Mauga
> "Mauga's whole gimmick that you burn and crit with Gunny and Cha-Cha respectively is interesting on paper but makes his ideal gameplay shooting in the general direction of the largest target. To make him require more aim and more positioning than currently, his chainguns now only shoot regular bullets and must be revved up before they can be fired."

Incendiary Chaingun (Gunny) and Volatile Chaingun (Cha-Cha):
- Removed burn and anti-burn crit special effects.
- Both chainguns now function as normal chainguns.
- Removed one-gun vs dual-gun firing toggle.
- Dual-fire spread tightened.
- Chainguns must be sufficiently revved before they can fire.
- Secondary fire revs chainguns.
- Primary fire while unrevved first revs, then fires.

Overrun:
- No longer fully unstoppable.
- Can be canceled by abilities that cancel Reinhardt charge.

Cage Fight:
- Ammo is infinite while active.
- Cage barrier blocks allied shots from outside unless allies enter the cage.

#### Junker Queen
> "Junker Queen's kit feels like it should owe itself to combos, but some parts are strangely modular. An automatically shot-by-shot reloading Scattergun removes some of the downtime taken to reload, and Carnage's additional damage to bleeding enemies turns her axe swing into a finishing blow. Rampage is an incredibly telegraphed ult as well, and making it unstoppable prevents it from being shut down before it even starts."

Scattergun:
- Reloads automatically one slug at a time (Scout TF2-style).

Carnage:
- Base damage lowered.
- Deals additional damage to bleeding enemies.

Rampage:
- Junker Queen becomes fully unstoppable while rampaging.

#### Orisa
> "Orisa's Javelin abilities make her seem like a displacement, disruption-based tank like Doomfist, but the existence of Fortify making her nearly invincible removes counterplay and pushes her towards being a generic frontline brawler. Taking cues from the lore in which she was designed to counter Doomfist, Orisa now has parallels to Doomfist's design, with her Fortify being more punishable yet giving Orisa Supercharged versions of her other abilities. Terra Surge provides an instant burst of health and temporary usage of old Fortify, functioning as a 'second life' much in the same way Meteor Strike does for Doomfist."

Energy Javelin / Supercharged Energy Javelin:
- Javelin can be held to charge projectile speed, damage, and knockback.

Javelin Spin / Supercharged Javelin Spin:
- Increased damage.
- Faster movement speed.

Fortify:
- Orisa can no longer attack during Fortify.
- Orisa can be knocked back during Fortify (hard CC still ignored).
- Damage reduction reduced.
- Effective hitbox slightly increased to absorb more damage.
- Blocking sufficient damage supercharges next Energy Javelin or Javelin Spin.
- Blocking sufficient damage also resets Javelin cooldowns.

Terra Surge:
- Grants temporary overhealth.
- Gradually restores Orisa to full health.
- Applies old Fortify benefits temporarily (no knockback, no CC, heavy damage reduction).

#### D.Va
> "D.Va fundamentally can't be balanced in her current state because Defense Matrix is the ultimate defensive ability, absorbing nearly everything except for a few types of attacks. This leads her to have limited mobility compared to other Dive tanks such as Wrecking Ball, Doomfist, and Winston purely because of the threat of an ult-vacuum cleaner flying around the map. Changing Defense Matrix from a resource to a flash parry on a short cooldown fits more into the high-APM gamer identity of D.Va while preventing stationary, frustrating gameplay. Increasing the duration of Boosters and adding the ability to temporarily speed boost it increases movement options, and tightening the spread of her Fusion Cannons makes her both less completely useless at range without Micro Missiles and more aim skill expressive. Which fits the type of elitist gamer Hana Song is."

Fusion Cannons:
- Precision Fusion perk added to base (tighter spread).

Boosters:
- Duration increased from 2 to 4 seconds.
- Press E while boosting to Gosokdo (고속도), speed boosting yourself.

Micro Missiles:
- Rebound to R.

Defense Matrix:
- Now a cooldown ability: 3 seconds.
- Flashes active for 1 second after use.
- Can absorb beam-type attacks.

New Major Perk: Gaesagi (개사기):
- During Self-Destruct, press Left Shift to manually control bomb movement and reduce blast radius.

### DPS

#### Junkrat
> "Junkrat's too often rewarded for doing the wrong thing due to the fact bouncing grenades and hitting them directly deal the same amount of damage, and a well-placed mine and a desperation mine do the same amount of damage. Requiring him to line up direct shots to get full value and arm his mine for potentially greater amounts of damage and self-launch than before increases his skill ceiling and reduces the exasperation you feel when he manages to nail a lucky grenade on you from behind three walls."

Frag Launcher:
- Grenades only deal direct-hit damage if they directly connect before any bounce.
- Bounced grenades always deal splash damage, even on direct contact.

Concussion Mine:
- Base damage decreased.
- Arming increases damage and self-launch velocity.

R.I.P. Tire:
- Nitro Boost perk added to base.

New Minor Perk: I'm Just Like You, Rocket Lady (replacing Nitro Boost):
- Hitting aerial enemies with grenades deals bonus damage.
- Also reloads one Frag Launcher shot.

#### Echo
> "Echo is hard to hear, and this combined with how her stickybombs give you a moment to realize you messed up isn't exactly fun."

- Echo now has clear movement sounds.

#### Sombra
> "Sombra was meant to be Overwatch's answer to TF2's Spy, but failed to realize that what made Spy balanced was his ability to get punished for making the wrong decision. Buffing Sombra's invisibility while removing the burst movement of Translocator allows her to stay in the backline longer, while making her more punishable for misplays. The removal of Virus and Hack's full ability disable (turning into a swift ability interrupt with ult-charge revealing powers) gets rid of the agency-removing parts of Sombra's kit while allowing for greater overall value to her team through information and the ability to cut the lights of dangerous enemy cooldowns, as well as a more consistent primary weapon."

Submachine Gun:
- Spread increased.
- Spread no longer blooms while firing.

Hack:
- Cast time reduced.
- No longer disables enemy abilities, but still interrupts/cancels them.
- Can be used while invisible.
- Temporarily reveals hacked enemy ultimate charge to your team.
- EMP-applied hacks still disable enemy abilities.

New Ability: Incognito:
- Full invisibility for up to 8 seconds.
- Taking damage cancels invisibility.
- Health packs refill portions of invisibility resource.
- Replaces Translocator.

Removed Ability: Virus.

New Minor Perk: Backstab (replacing Encrypted Upload):
- Breaking invisibility by shooting increases SMG fire rate for 3 seconds.

Minor Perk: CTRL ALT ESC:
- Using Incognito below half health immediately starts passive regeneration.

New Major Perk: Power Outage (replacing Viral Replication):
- Hacking one enemy also hacks up to two nearby enemies.

#### Venture
> "Venture was promised as a new version of DPS Doomfist, and although they were effective in reducing the sheer burst damage of Doomfist to much more manageable combos, they still lack the movement depth that DPS Doomfist was so beloved for. Adding momentum canceling tech and an equivalent to old Seismic Slam through a revamped Burrow increases Venture's overall skill ceiling while a change to their passive keeps them from getting guaranteed value from pressing funny buttons."

Drill Dash:
- Reduced initial and follow-up damage.
- Press jump at any time during Drill Dash to cancel and keep horizontal/vertical momentum (Rocket Punch cancel-style).

Burrow:
- Entering Burrow damages nearby enemies.
- Enter damage scales with starting height (25 to 100).
- Press jump at any time during emergence to cancel and keep vertical momentum (Seismic Slam cancel-style).
- Reduced emergence damage.

Explorer's Resolve:
- Grants shields only on ability hits, not ability usage.

#### Soldier: 76
> "Soldier: 76 falls behind other hitscan heroes like Cassidy, Sojourn, and Emre because he lacks an identity other than Gun: Shoot. Based on his already great ground movement through Sprint, the buff to Helix Rockets to allow greater self-propulsion makes him an aggressive, hyper-mobile hitscan and pushes him away from being a generalist."

New Ability: Stim Pack:
- Heals Soldier: 76 over time.
- Increases attack speed.
- Replaces Biotic Field.

Helix Rockets:
- Increased self-propulsion for true rocket-jumping.

New Major Perk: Triple Salvos (replacing Stim Pack):
- Helix Rockets gain three charges.
- Per-rocket damage severely reduced so all three together equal one normal Helix Rocket.

#### Pharah
> "Pharah has seen buffs to her rocket jumping throughout the years, and it makes more sense to lean into that identity rather than turning her into a purely sky-bound hero. This alleviates the problem where a Pharah either instantly dies because of an enemy hitscan or dominates the lobby because the enemies are using entirely projectile heroes."

Rocket Launcher:
- Rocket self-propulsion increased (TF2-style rocket jumping).
- Rocket self-damage decreased.

Removed Ability: Jet Dash.

Jump Jet:
- No longer grants fuel on use.

#### Genji
> "Nanoblade keeps Dragonblade from being a heavily skill-expressive ultimate and forces it to be balanced around whether or not an Ana has Nano Boost ready to go. Buffing Dragonblade itself by increasing its duration while removing the ability to be Nano Boosted makes the ultimate far more reliant on skill than it currently is."

Dragonblade:
- Duration increased from 6 to 7 seconds.
- On activation, Genji is restored and cleansed of all beneficial effects.
- While Dragonblading, Genji cannot receive beneficial effects (for example, Suzu or Nano Boost).
- Negative effects can still be applied during Dragonblade.

#### Reaper
> "Despite having the character fantasy of being a stealthy assassin, much of Reaper's gameplay revolves around sticking with your tank and melting the other team's tank with a shotgun spread the size of New Zealand. Giving him a quicker Shadow Step and far more maneuverable Wraith Form gives Reaper much-needed mobility, to perform well as a flanker, while a tightened spread and reduced damage reduces his effectiveness against tanks while increasing it against squishier enemies."

- Hero health reduced from 300 to 250.

Hellfire Shotguns:
- Spread tightened.
- Damage reduced.

Removed Ability: Dire Triggers (Long Range Dual Shot).

Shadow Step:
- Shadow Blink perk added to base (faster cast, shorter max range).

Wraith Form:
- Reaper becomes a low-lying black mist cloud.
- Jump height increased while wraithing (Moira Fade-like movement).

Death Blossom:
- Ultimate charge cost increased.

New Major Perk: Surprise Party (replacing Shadow Blink):
- Exiting Shadow Step briefly makes Reaper unstoppable.
- Also reloads Hellfire Shotguns.

New Major Perk: Force-a-Death:
- Hellfire Shotguns become Force-a-Nature-style.
- Enables shotgun jumping and knockback on enemies.

#### Anran
> "Anran's lack of powerful movement makes her into what's effectively a worse Genji, especially in higher ranks where her reliance on clumped-up enemies is exposed. Making Inferno Rush quicker and fully maneuverable gives extra mobility so that she can stay a viable choice. Dancing Blaze is an invulnerability tool that keeps Anran in the fight, so removing its full invincibility is necessary as her overall survivability increases with better mobility."

Inferno Rush:
- Speed increased.
- Full vertical movement added.
- Carries horizontal and vertical momentum after ending.

Dancing Blaze:
- No longer fully invincible.
- Incoming damage is reduced during Dancing Blaze.

### Support

#### Moira
> "Moira has the lowest skill floor and skill ceiling difference in the game due to the fact it's incredibly easy to play her while being completely impossible to improve as her other than maybe bouncing your orbs better. Switching the aiming methods of her healing and dealing adds tracking skill while also improving healing consistency, and an overall buff to her damage and a nerf to the invulnerability of Fade rewards skill and punishes bad decisions."

Biotic Grasp:
- Locks onto heal target.
- Provides reduced splash healing to allies around that target.
- Changed from forward spray.

Biotic Grasp Alt Fire:
- Short-range beam requiring aim tracking.
- Damage increases the longer target tracking is maintained.
- Changed from auto-lock style.

Fade:
- Moira remains invisible but is no longer invincible during Fade.
- Gains increased damage resistance while fading.

#### Mercy
> "Mercy has often been described as a spectator in a game where everyone else is constantly making decisions on the fly. Rather than nerf her movement, the most expressive part of her kit, damage boost has been entirely removed to eliminate pocketing and her pistol has been buffed so that she can more easily provide value through switching to her sidearm. Valkyrie hasn't been much of an impactful ultimate as well, so switching it into what's basically TF2 Medic's Quick Fix Uber grants her far more fight saving potential: fitting for the woman wearing the robotic angel suit."

Caduceus Staff:
- Secondary-fire damage boost removed.

Caduceus Blaster:
- Swap speed increased.
- Secondary fire can be used at any time to swap between Staff and Blaster.
- Changed from projectile to hitscan with slight spread.

Removed Ultimate: Valkyrie.

New Ultimate: Heroes Never Die:
- Tremendously increases primary staff healing rate.
- Makes healing target unstoppable.

#### Ana
> "Ana's Biotic Grenade makes or breaks a meta due to the fact it can be applied to up to 5 enemies at once, negating entire support compositions. Reducing its cooldown while making it so that it only serves as burst healing reduces these one-button fight winning moments. Sleep Dart, due to often being comboed with Biotic Grenade, now has the anti-heal effect latched onto it, giving Ana more defense against flankers while keeping her counterplay against healing-reliant single targets, such as Mauga."

Biotic Grenade:
- Cooldown reduced from 12 to 10 seconds.
- Anti-heal effect removed.

Sleep Dart:
- Slept target is anti-healed.

#### Kiriko
> "Protection Suzu has long been the reason Kiriko's stayed in the meta for so long not just for its cleanse but because a well-timed one can completely negate entire ultimates or powerful attacks like Mauga's stomp or Doomfist's Empowered Punch. Reducing its cooldown and healing while removing invincibility makes it less fight-swingy while improving Kiriko's AOE healing. Swift Step is too often a tool to leave bad situations rather than a tool to assist flankers, so giving it a cast time while reducing its cooldown makes it more frequent while preventing it from becoming a get-out-of-jail-free card."

Swift Step:
- Cooldown reduced from 7 to 5 seconds.
- Now has a cast time (similar to Reaper Shadow Step).

Protection Suzu:
- Cooldown reduced from 14 to 12 seconds.
- No longer grants temporary invincibility.
- Burst healing increased.

## Notes

- This README is a design specification and balancing target list.
- Workshop implementation details may differ during iteration.
- Values and behavior should be tuned through playtesting and feedback.
