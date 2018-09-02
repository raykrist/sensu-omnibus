### arm

This is testet on Raspberry Pi with debian stretch.

#### Running a build

1. Clone the sensu-omnibus git repository:

  ```sh
  git clone https://github.com/sensu/sensu-omnibus.git
  ```

2. Change to the sensu-omnibus directory:

  ```sh
  cd sensu-omnibus
  ```

3. Check out the desired tag of sensu-omnibus, e.g. `v1.2.0-1` branch:

  ```sh
  git checkout v1.2.0-1
  ```

4. Set `use_git_caching false` in `omnibus.rb`

5. Install gem dependencies:

  ```sh
  bundle install --path vendor/bundle
  ```

6. Export version environment variables:

  ```sh
  export SENSU_VERSION=x.y.z
  export BUILD_NUMBER=1
  ```

7. Build Sensu:

  ```sh
  bundle exec omnibus build sensu -l debug
  ```
