# auto-green

[![Build Status](https://github.com/alterem/auto-green/workflows/ci/badge.svg?branch=main)](https://github.com/alterem/auto-green/actions)

Keep GitHub commit status always green automatically.

> a commit a day keeps your girlfriend away.

## Principle

Use the scheduling feature in GitHub Actions to automatically run every period of time `git commit`，The information submitted is "a commit a day keeps your girlfriend away"，Inspired by Zhihu Question[在 GitHub 上保持 365 天全绿是怎样一种体验？](https://www.zhihu.com/question/34043434/answer/57826281) Response from an anonymous user:

> Used to keep a 200 day plus green streak, but have neglected my girlfriend, now I have the ultimate green streak.

## Usage

- Copy this GitHub repository by clicking the **Use this template** button in the top-right corner，**:warning: Don't Fork It, Forked Repos Don't Make You Green :warning:**
- In your project, go into the project's GitHub Actions page by clicking the **Actions** tab at the top and click the green button “**I understand my workflows, go ahead and enable them**” Turn on Auto-Commit
- Modify [line 19, 20 of the ci.yml file](https://github.com/justjavac/auto-green/blob/master/.github/workflows/ci.yml#L19) with your GitHub account and nickname
- (Optional) You can adjust the frequency by modifying the 8th line of the [ci.yml file](https://github.com/justjavac/auto-green/blob/master/.github/workflows/ci.yml#L8).

A cron job syntax has five fields separated by spaces, each representing a unit of time.

```plain
┌───────────── minute (0 - 59)
│ ┌───────────── hour (0 - 23)
│ │ ┌───────────── day of month (1 - 31)
│ │ │ ┌───────────── month (1 - 12 or JAN-DEC)
│ │ │ │ ┌───────────── day of week (0 - 6 or SUN-SAT)
│ │ │ │ │
│ │ │ │ │
│ │ │ │ │
* * * * *
```
What each time field means:

| Symbol| Description | Sample                                 |
| -----| -----------| --------------------------------------|
| `*`  | Any value  | `* * * * *` Every minute of every hour every day |
| `,`  | Value separator | `1,3,4,7 * * * *` Every minute at 1, 3, 4, 7 past the hour  |
| `-`  | Range      | `1-6 * * * *` Every minute from 1 through 6 past the hour |
| `/`  | Every     | `*/15 * * * *` Every 15 minutes                 |

**Note:** Due to GitHub Actions' limitation, setting it to `* * * * *` will result in a practical execution every 5 minutes.

## License

[auto-green](https://github.com/justjavac/auto-green) is released under the MIT License. See the bundled [LICENSE](./LICENSE) file for details.
